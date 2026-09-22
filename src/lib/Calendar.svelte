<!-- Generates a calendar from the lecture data in the yaml -->

<script>
  import moment from 'moment';
  import BoxLink from './BoxLink.svelte';
  import Day from './Calendar/Day.svelte';
  import Assignments from './Calendar/Day/Assignments.svelte';
  import Materials from './Calendar/Day/Materials.svelte';
  import Topic from './Calendar/Day/Topic.svelte';
  import Week from './Calendar/Week.svelte';

  import {
    class_data,
    fixupLink,
    getBoxColor,
    getLectureMoment,
    lectures_by_week
  } from './classData';

  const weekdays = class_data.class_days.length;

  function assignmentsForLecture(lectureIndex) {
    const lecture = class_data.lectures[lectureIndex];
    const nextLecture = class_data.lectures[lectureIndex + 1];
    const weekStart = moment(lecture.date, 'YYYY/MM/DD').startOf('day');
    const weekEnd = nextLecture
      ? moment(nextLecture.date, 'YYYY/MM/DD').startOf('day')
      : weekStart.clone().add(1, 'week');

    return class_data.assignments.filter((assignment) => {
      const due = moment(assignment.due, 'YYYY/MM/DD').startOf('day');
      return due.isSameOrAfter(weekStart) && due.isBefore(weekEnd);
    });
  }

  function formatDueDate(date) {
    return moment(date, 'YYYY/MM/DD').format('MMM D');
  }
</script>

<div class="calendar">
  {#each lectures_by_week as lectures, i}
    <Week number={i + 1} future={getLectureMoment(i * weekdays).isAfter(moment())}>
      {#each lectures as lecture, j}
        <Day
          date={getLectureMoment(i * weekdays + j).format('ddd, MMM D')}
          holiday={!!lecture.holiday}
          even={j % 2 == 0}
        >
          <Topic>
            {#if lecture.holiday}
              <em>{lecture.topic}</em>
            {:else}
              {lecture.topic}
            {/if}
          </Topic>
          {#if lecture.materials}
            <Materials>
              {#each Object.entries(lecture.materials) as [type, url]}
                <BoxLink href={fixupLink(url)} color={getBoxColor(type)} external={url.startsWith('http')}>
                  {type}
                </BoxLink>
              {/each}
            </Materials>
          {:else}
            <Materials />
          {/if}
          <Assignments>
            {#each assignmentsForLecture(i * weekdays + j) as assignment}
              {#if assignment.url}
                <a class="deadline" href={fixupLink(assignment.url)}>
                  <span>{assignment.name}</span>
                  <small>Due {formatDueDate(assignment.due)}</small>
                </a>
              {:else}
                <span class="deadline">
                  <span>{assignment.name}</span>
                  <small>Due {formatDueDate(assignment.due)}</small>
                </span>
              {/if}
            {/each}
          </Assignments>
        </Day>
      {/each}
    </Week>
  {/each}
</div>

<style>
  .calendar {
    margin-top: 20px;
  }

  .deadline {
    display: inline-flex;
    flex-direction: column;
    line-height: 1.25;
  }

  .deadline small {
    color: #666;
  }
</style>
