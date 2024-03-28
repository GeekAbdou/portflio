<template>
  <div class="container" id="home">
    <div class="user-profile">
      <div class="user-profile__card">
        <div class="user-profile__greeting">Hi 👋</div>
        <h1 class="user-profile__name">I'am <span>Abdelrahman</span></h1>
        <div class="user-profile__role">Frontend Developer</div>

        <div class="social">
          <div class="user-profile__social-links">
            <a
              class="user-profile__social-link user-profile__social-link--linkedin"
              href="https://www.linkedin.com/in/geekabdo/"
              target="_blank"
              title="linkedin"
              rel="noopener"
            >
              <img src="../assets/svg/linkedin.svg" alt="LinkedIn" />
            </a>
            <a
              class="user-profile__social-link user-profile__social-link--github"
              href="https://github.com/GeekAbdou"
              target="_blank"
              rel="noopener"
              title="github"
            >
              <img src="../assets/svg/github.svg" alt="LinkedIn" />
            </a>
            <a
              class="user-profile__social-link user-profile__social-link--leetcode"
              href="https://leetcode.com/GeekAbdo/"
              title="leetcode"
              target="_blank"
            >
              <img src="../assets/svg/leetcode.svg" alt="LinkedIn" />
            </a>
            <a
              class="user-profile__social-link user-profile__social-link--codeforces"
              href="https://codeforces.com/profile/_Levi_"
              title="codeforces"
              target="_blank"
            >
              <img src="../assets/svg/codeforces.svg" alt="LinkedIn" />
            </a>
            <a
              class="user-profile__social-link user-profile__social-link--email"
              href="mailto:geek.abdoo@gmail.com"
              title="gmail"
              target="_blank"
            >
              <img src="../assets/svg/email.svg" alt="LinkedIn" />
            </a>
            <a
              class="user-profile__social-link user-profile__social-link--telephone"
              href="+201094668220"
              title="telephone"
              target="_blank"
            >
              <img src="../assets/svg/telephone.svg" alt="LinkedIn" />
            </a>
          </div>
        </div>
      </div>

      <div class="user-profile__avatar">
        <img alt="my avatar" src="../assets/abdelrahman.png" />
      </div>
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
.container {
  display: flex;
  justify-content: space-between;
}

.user-profile {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 2rem;
  height: calc(100vh + 60px);
  margin: 0 auto;

  &__greeting,
  &__name,
  &__role {
    font-size: calc(1.5rem + 1.8vw);
    color: #000;
    font-weight: 700;
    margin: -16px 0px;

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
    gap: 1rem;
    margin-top: 1rem;
  }

  &__social-link {
    img {
      width: calc(1rem + 0.8vw);
      height: calc(1rem + 0.8vw);
    }
  }

  &__avatar {
    width: 350px;
    height: 350px;
    border-radius: 50%;
    overflow: hidden;
    border: 5px solid #12b886;
    margin-left: 120px;

    img {
      width: 100%;
    }
  }
}

@media screen and (min-width: 300px) and (max-width: 900px) {
  .user-profile {
    flex-direction: column;
    margin: 0 auto;
    height: 100vh;

    &__card {
      margin: auto 0;
    }
    &__avatar {
      display: none;
    }
  }
}
</style>
