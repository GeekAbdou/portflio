<template>
  <div class="user-profile">
    <div class="user-profile__card">
      <div class="user-profile__greeting">Hi 👋</div>
      <h1 class="user-profile__name">I'am <span>Abdelrahman</span></h1>
      <div class="user-profile__role">Frontend Developer</div>

      <div class="user-profile__social-links">
        <a
          class="user-profile__social-link user-profile__social-link--linkedin"
          href="http://linkedin.com/in/mohammed-taysser"
          target="_blank"
          title="linkedin"
          rel="noopener"
        ></a>
        <a
          class="user-profile__social-link user-profile__social-link--github"
          href="https://github.com/mohammed-Taysser"
          target="_blank"
          rel="noopener"
          title="github"
        ></a>
        <a
          class="user-profile__social-link user-profile__social-link--leetcode"
          href="mailto:mohamedtaysser983@gmail.com"
          title="gmail"
          target="_blank"
        ></a>
        <a
          class="user-profile__social-link user-profile__social-link--codeforces"
          href="mailto:mohamedtaysser983@gmail.com"
          title="gmail"
          target="_blank"
        ></a>
        <a
          class="user-profile__social-link user-profile__social-link--email"
          href="mailto:mohamedtaysser983@gmail.com"
          title="gmail"
          target="_blank"
        ></a>
        <a
          class="user-profile__social-link user-profile__social-link--telephone"
          href="mailto:mohamedtaysser983@gmail.com"
          title="gmail"
          target="_blank"
        ></a>
      </div>
    </div>

    <div class="user-profile__avatar">
      <img alt="my avatar" />
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
.user-profile {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 2rem;
  background: white;
  height: calc(100vh - 100px);

  &__greeting,
  &__name,
  &__role {
    font-size: calc(1.475rem + 2.7vw);
    color: #333;
    font-weight: 700;
    span {
      font-weight: 700;
      background-size: 100% 100%;
      outline: 0;
      background-image: linear-gradient(transparent 50%, rgba(18, 184, 134, 0.2) 50%);
      color: #12b886;

      &:hover {
        background-size: 0% 100%;
      }
    }
  }

  &__social-links {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin-bottom: 2rem;

    &--linkedin,
    &--github,
    &--email {
      width: 3rem;
      height: 3rem;
      background-size: contain;
      background-repeat: no-repeat;
      display: block;
    }
    /*
    &--linkedin {
      background-image: url('/path-to-linkedin-icon.svg'); // Update with actual path.
    }

    &--github {
      background-image: url('/path-to-github-icon.svg'); // Update with actual path.
    }
    &--leetcode {
      background-image: url('/path-to-email-icon.svg'); // Update with actual path.
    }
    &--codeforces {
      background-image: url('/path-to-email-icon.svg'); // Update with actual path.
    }
    &--email {
      background-image: url('/path-to-email-icon.svg'); // Update with actual path.
    }
    &--telephone {
      background-image: url('/path-to-email-icon.svg'); // Update with actual path.
    }*/
  }

  &__avatar {
    width: 200px; // Set the size of the avatar image container.
    height: 200px;
    border-radius: 50%;
    overflow: hidden;
    border: 5px solid #ccc; // This should match the border color in the image.
    img {
      width: 100%;
      height: auto;
    }
  }
}
</style>
