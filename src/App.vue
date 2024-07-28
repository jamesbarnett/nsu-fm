<script setup>
import { ref } from 'vue'

const email = ref("")

/*window.addEventListener("load", (e) => {
  const form = document.querySelector(".newsletter-cta form")
  console.log(`got the form: ${form}`);

  const email = document.getElementById("email")
  console.log(`Email: ${email}`)
  form.addEventListener("submit", (e) => {
    console.log(`Handler called: ${email.value}`)
    console.dir(email.value)
    if (email.value === "" || name.value === null) {
      console.log(`prevented default ${document}`)
      e.preventDefault()
      const error = document.querySelector(".form-group span:last-child")
      error.style.display = "block"
    }
  })
});*/

</script>

<template>
  <div class="newsletter-cta">
    <picture>
      <source media="(min-width: 48rem)" srcset="/assets/images/illustration-sign-up-desktop.svg">
      <img src="/assets/images/illustration-sign-up-mobile.svg" alt="">
    </picture>
    <div class="content">
      <h1 class="title">Stay updated!</h1>
      <p>Join 60,000+ product managers receiving monthly updates on:</p>

      <ul role="list" class="checkmark-list">
        <li>Product discovery and building what matters</li>
        <li>Measuring to ensure updates are a success</li>
        <li>And much more!</li>
      </ul>
      <form action="thanks">
        <div class="form-group with-error-field">
          <label for="email">Email address</label>
          <input v-model="email" placeholder="email@company.com" type="email" id="email">
          <span class="error">Valid email required</span>
        </div>
        <button class="button">Subscribe to monthly newsletter</button>
      </form>
    </div>
  </div>
</template>

<style scoped>
input {
  padding: 1rem;
  border-radius: 0.5rem;
  font: inherit;
  font-size: var(--fs-400);
  font-weight: var(--fw-regular);
  border: 1px solid var(--clr-neutral-200);
}

input::placeholder {
  color: var(--clr-neutral-200);
}

input:not(:focus):invalid {
  color: var(--clr-accent-400);
  border: 1px solid var(--clr-accent-400);
  background: hsl(4 100% 66% / 0.2);
}

.form-group {
  display: grid;
  gap: 0.5rem;
  font-size: var(--fs-300);
  font-weight: var(--fw-bold);
}

.form-group>.error {
  grid-row: 1;
  grid-column: 2;
  text-align: end;
  color: var(--clr-accent-400);
  display: none;
}

.form-group> :not(:focus):invalid+.error {
  display: block;
  background: hsl(4, 100%, 67% / 0.2);
}

.form-group.with-error-field {
  grid-template-columns: 1fr 1fr;
}

.form-group.with-error-field>input {
  grid-column: 1 / -1;
}

.button {
  background: var(--clr-neutral-800);
  color: var(--clr-neutral-100);
  font: inherit;
  font-weight: var(--fw-bold);
  border: 0;
  padding: 1rem;
  border-radius: 0.5rem;
  width: 100%;
}

.button:hover,
.button:focus-visible {
  position: relative;
  background-image: linear-gradient(-90deg,
      var(--clr-accent-400),
      var(--clr-accent-500),
    );
}

form {
  isolation: isolate;
}

.button:hover::after,
.button:focus-visible:after {
  content: "";
  position: absolute;
  z-index: -1;
  inset: 0;
  background: inherit;
  border-radius: inherit;
  translate: 0 1.0rem;
  filter: blur(1rem);
  opacity: .25;
}

.checkmark-list {
  display: grid;
  gap: 0.625rem;
}

.checkmark-list li {
  display: grid;
  grid-template-columns: 2.5rem auto;
}

.checkmark-list li::before {
  content: url("/assets/images/icon-list.svg");
}

.newsletter-cta {
  max-width: 1110px;
  border-radius: 1rem;
  background-color: var(--clr-neutral-100);
}

@media (min-width: 48rem) {
  .newsletter-cta {
    margin-inline: 1rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .newsletter-cta>.content {
    grid-column: 1;
    grid-row: 1;

  }

  .newsletter-cta picture {
    place-content: center;
  }

  .newsletter-cta .title {
    margin-block-end: 0;
  }
}

.newsletter-cta>.content {
  display: grid;
  gap: 1rem;
  padding: 1.5rem;
}

.newsletter-cta .title {
  font-size: var(--fs-900);
  font-weight: var(--fw-bold);
}

.newsletter-cta img {
  margin-inline: auto;
}

.newsletter-cta form {
  margin-block-start: 1.25rem;
  display: grid;
  gap: 1.5rem;
}
</style>
