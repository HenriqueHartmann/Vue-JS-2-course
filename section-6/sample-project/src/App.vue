<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <announcement></announcement>
        <app-article></app-article>
        <app-contact>
          <p>Some content</p>
          <p slot="top">Contact us and one of our representatives will get back to you as soon as possible.</p>
          <p slot="bottom">Plese do not submit any sensitive information.</p>
        </app-contact>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>
