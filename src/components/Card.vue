
<script setup>
</script>

<template>
  <div class="card-wrapper">
    <article class="card">
      <img src="../assets/images/illustration-woman-online-mobile.svg" alt="Woman looking at screen">
      <h1>FAQ</h1>
      <ul>
        <li>
          <details>
            <summary>How many team members can I invite?</summary>
            <p>You can invite up to 2 additional users on the Free plan. There is
              no
              limit on team members for the Premium plan.</p>
          </details>
        </li>
        <li>
          <details>
            <summary>What is the maximum file upload size?</summary>
            <p>No more than 2GB. All files in your account must fit your allotted
              storage space.</p>
          </details>
        </li>
        <li>
          <details>
            <summary>How do I reset my password?</summary>
            <p>Click “Forgot password” from the login page or “Change password”
              from
              your profile page. A reset link will be emailed to you.</p>
          </details>
        </li>
        <li>
          <details>
            <summary>Can I cancel my subscription?</summary>
            <p>Yes! Send us a message and we’ll process your request no questions
              asked.</p>
          </details>
        </li>
        <li>
          <details>
            <summary>Do you provide additional support?</summary>
            <p>Chat and email support is available 24/7. Phone lines are open
              during
              normal business hours.</p>
          </details>
        </li>
      </ul>
    </article>
  </div>
</template>

<style scoped lang="scss">
.card-wrapper {
  position: relative;
}
.card {
  width: 75vw;
  max-width: 500px;
  background: white;
  padding: 1.5rem;
  border-radius: 1rem;
  // overflow: hidden;

  img {
    position: absolute;
    // top: 0;
    // left: 50%;
    // transform: translate(-50%, -60%);
    z-index: 2;
    filter: drop-shadow( 0px 24px 0px hsl(240, 73%, 65%, 0.2));
  }


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
  }

  li {
    list-style: none;
    padding-block: 1rem;
    border-bottom: 1px solid var(--clr-light-grayish-blue);
  }

  details {
    p {
      margin-block-start: 0.5rem;
    }
  }

  summary {
    display: flex;
    cursor: pointer;

  }

  summary::after {
    margin-inline-start: auto;
    transition: transform 250ms ease;
    content: url('../assets/images/icon-arrow-down.svg')
      /* chevron */
  }

  details[open] summary {
    color: var(--clr-very-dark-desaturated-blue);
    font-weight: var(--fw-bold);
    // transform: rotate(90deg);
  }

  details[open] summary::after {
    transform: rotate(180deg);
  }
}
</style>