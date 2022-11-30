
<script setup>
import { ref } from 'vue';

const openIx = ref(0)

function onToggle(e, ix) {
  if (e.target.open) {
    openIx.value = ix
  } else if (openIx.value === ix) {
    openIx.value = -1
  }
}

const data = [
  {
    question: "How many team members can I invite?",
    answer: "You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan."
  },
  {
    question: "What is the maximum file upload size?",
    answer: "No more than 2GB. All files in your account must fit your allotted storage space."
  },
  {
    question: "How do I reset my password?",
    answer: "Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you."
  },
  {
    question: "Can I cancel my subscription?",
    answer: "Yes! Send us a message and we’ll process your request no questions asked."
  },
  {
    question: "Do you provide additional support?",
    answer: "Chat and email support is available 24/7. Phone lines are open during normal business hours."
  }
]


</script>

<template>
  <div class="card-wrapper">
    <img src="../assets/images/illustration-woman-online-mobile.svg"
      alt="Woman looking at screen">
    <div class="card-wrapper__background" />
    <article class="card">
      <h1>FAQ</h1>
      <ul>
        <li v-for="(qa, ix) in data" :key="ix">
          <details @toggle="onToggle($event, ix)" :open="openIx === ix ? true : null">
            <summary>{{ qa.question}}</summary>
            <p>{{ qa.answer }}</p>
          </details>
        </li>
      </ul>
    </article>
  </div>
</template>

<style scoped lang="scss">
.card-wrapper {
  --card-padding: 1.5rem;

  display: grid;
  grid-template-columns: 1fr 3.5fr 1fr;
  grid-template-rows: repeat(4, auto);

  &>img {
    grid-row: 1 / span 2;
    grid-column: 2;
    // max-width: 100px;
    // margin: auto;
    transform: translate(0, -10%);
    z-index: 2;
    filter: drop-shadow(0px 24px 0px hsl(240, 73%, 65%, 0.2));
  }

  &__background {
    grid-row: 2 / -1;
    grid-column: 1 / -1;
    z-index: 1;
    background: white;
    padding: var(--card-padding);
    border-radius: 1rem;
  }

  .card {
    margin-block-start: 1rem;

    max-width: 700px;

    grid-row: 3 / -1;
    grid-column: 1 / -1;

    display: grid;
    gap: 1rem;

    padding: var(--card-padding);
    z-index: 2;

    h1 {
      color: var(--clr-very-dark-desaturated-blue);
      font-size: 2.5rem;
      font-weight: var(--fw-bold);
      margin: auto;
    }

    ul {
      display: flex;
      flex-direction: column;
      padding: 0;
      margin-block-end: 1rem;

      li {
        list-style: none;
        padding-block: 1rem;
        border-bottom: 1px solid var(--clr-light-grayish-blue);
      }
    }


    details {
      p {
        font-size: 0.9rem;
        margin-block-start: 0.5rem;
      }

      summary {
        display: flex;
        align-items: start;
        gap: 1rem;
        cursor: pointer;

        &::after {
          margin-inline-start: auto;
          transition: transform 250ms ease;
          content: url('../assets/images/icon-arrow-down.svg')
        }
      }


      &[open] summary {
        color: var(--clr-very-dark-desaturated-blue);
        font-weight: var(--fw-bold);

        &::after {
          transform: rotate(180deg);
        }
      }
    }
  }
}
</style>

