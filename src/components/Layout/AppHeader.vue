<template>
  <header
    :class="scrolled ? 'scroll' : ''"
    class="header"
    style="z-index: 1000"
  >
    <div class="container">
      <div class="header__wrapper">
        <router-link style="text-decoration: none" link to="/">
          <div class="header__logo">
            <div>
              <h1>Dilpreet Blog</h1>
            </div>
          </div>
        </router-link>
        <div class="header__right">
          <div class="header__right--phone">
            <router-link style="text-decoration: none" link to="/about">
          <div class="header__logo">
            <div>
              <h1>About Us</h1>
            </div>
          </div>
        </router-link>
          </div>

          <div class="header__right--place">
            <div></div>
            <router-link style="text-decoration: none" link to="/contact">
          <div class="header__logo">
            <div>
              <h1>Contact</h1>
            </div>
          </div>
        </router-link>
          </div>

        </div>
      </div>
    </div>
  </header>
</template>
<script>
import { BDropdown, BDropdownItem, BIcon } from "bootstrap-vue";

export default {
  comments: { BDropdown, BDropdownItem, BIcon },
  name: "AppHeader",

  data() {
    return {
      scrolled: false,
      popUpMenu: false,
      langvalue: "",
      selectedLocale: 2,
      supportedLocales: [
        { id: 1, name: this.$t("uzCyrillic") },
        { id: 2, name: this.$t("uzLang") },
        { id: 3, name: this.$t("russianLanguage") },
      ],
    };
  },

  methods: {
    handleScroll() {
      this.scrolled = window.scrollY > 0;
    },
    changeLocale() {
      if (this.selectedLocale == 1) {
        this.langvalue = "uzCyrillic";
      } else if (this.selectedLocale == 2) {
        this.langvalue = "uzLang";
      } else {
        this.langvalue = "russianLanguage";
      }
      console.log(this.langvalue);
      this.$i18n.locale = this.langvalue;
    },
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
    this.$i18n.locale = this.langvalue;
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>
<style lang="scss">
.header {
  position: sticky;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1;
  display: flex;
  align-items: center;
  min-height: 80px;
  background-color: $color-white;
  border-bottom: 1px solid $color-primary-light;
  transition: box-shadow 0.25s ease-in-out;

  &__wrapper {
    font-family: $base-font;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__logo {
    display: flex;
    align-items: center;
    gap: 15px;
    font-family: $base-font;
    font-size: 19px;
    letter-spacing: 1.5px;

    &--elegant {
      color: $color-dark;
    }

    &--shoes {
      color: $color-primary;
    }
  }

  &__right {
    display: flex;
    align-items: center;
    font-family: $base-font;

    &--place {
      display: flex;
      align-items: center;
      margin-right: 30px;
      cursor: pointer;

      & > div {
        margin-right: 6px;
      }
    }

    &--phone {
      display: flex;
      align-items: center;
      cursor: pointer;

      & > div {
        margin-right: 6px;
      }

      a {
        margin-right: 16px;
      }
    }

    &--lang {
      cursor: pointer;
    }

    &--mobileMenuIcon {
      display: none;
    }
  }
}
.scroll {
  box-shadow: 0 0 10px rgba(168, 168, 168, 0.4);
}
.Select {
  width: 48px;
  height: auto;
  cursor: pointer;
  color: #4d5fff;
  border-radius: 5px;
  border: 1px solid #4d5fff;
}

.categoryCard {
  display: none;
}

// =========Mobile breakpoint==========
@media screen and (max-width: 768px) {
  .header {
    &__logo {
      &--elegant {
        display: none;
      }
      &--shoes {
        display: none;
      }
    }

    &__right {
      &--place {
        margin-right: 10px;
        & > a {
          margin-right: 2px;
          background-color: #edeef2;
          padding: 8px;
          border-radius: 10px;
        }

        span {
          display: none;
        }
      }

      &--phone {
        margin-right: 10px;
        & > a {
          margin-right: 2px;
          background: #edeef2;
          padding: 8px;
          border-radius: 8px;
        }

        span {
          display: none;
        }
      }

      &--lang {
        background: #edeef2;
        padding: 8px;
        border-radius: 8px;
        margin-right: 10px;
      }

      &--mobileMenuIcon {
        display: block;
        background: #edeef2;
        padding: 8px;
        border-radius: 8px;
      }
    }
  }

  .categoryCard {
    display: block;
  }
}
</style>
