<script>
  import { faqContent } from "./faqContent.js";
  let inputQuestion = "";
  let selectedAnswer = "";

  function searchAnswer() {
    const foundFAQ = faqContent.find(faq =>
      faq.question.toLowerCase().includes(inputQuestion.toLowerCase())
    );
    selectedAnswer = foundFAQ ? foundFAQ.answer : "No matching question found. Please try again.";
  }
</script>

<style>
  /* Add your styles here */
</style>

<div>
  <h2>Type the name of the menu that you need help with:</h2>
  <input
    type="text"
    placeholder="Type your question"
    bind:value="{inputQuestion}"
    on:keydown="{e => (e.key === 'Enter' ? searchAnswer() : null)}"
  />
  <button on:click="{searchAnswer}">Search</button>
  <div>
    <p>{selectedAnswer}</p>
  </div>
</div>
