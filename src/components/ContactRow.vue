<template>
  <section id="contact" class="py-10">
    <div class="container">
      <div class="row jc-center">
        <div class="col-s-12 col-l-8">
          <h2 class="text-center">Contact</h2>
          <form action="" class="jc-flex-end text-left">
            <label for="name">Name</label>
            <input type="text" name="name" id="name" />
            <label for="email">Email</label>
            <input type="email" name="email" id="email" />
            <label for="subject">Subject</label>
            <input type="text" name="subject" id="subject" />
            <label for="message">Name</label>
            <textarea name="message" id="message" cols="30" rows="10"></textarea>
            <button type="submit" class="mt-2 primary-background light-color">Send message</button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
#contact {
  background-color: #2c3e50;
}
</style>
