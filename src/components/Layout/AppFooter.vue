<template>
  <footer>
    <div class="container">
      <div class="footerContent">
        <div class="footerContent__logo">
          <h3>Dilpreet Blog</h3>
        </div>

        <div class="footer__top">
          <h6>{{ $t("Dilpreet Blogging") }}</h6>
          <ul>
            <li>
              <a class="AboutUs" href="#">{{ $t("About Us") }}</a>
            </li>
            <li>
              <a class="ContactUs" href="#">{{ $t("Contact") }}</a>
            </li>
          </ul>
        </div>

        <div class="footer__top">
          <h6>{{ $t("Dillpreet Blog") }}</h6>
          <ul>
            <li>
              <a href="#">
                <b-icon style="color: #fff" icon="telephone"></b-icon>
                <a
                  href="tel:+611234567890"
                  style="text-decoration: none"
                  class="socialLinkText"
                >+61 123457890</a>
              </a>
            </li>
            
            <li>
              <a target="_blank" href="#">
                <b-icon style="color: #fff" icon="briefcase"></b-icon>
                <span class="socialLinkText">
                  {{
                  $t("info@dilpreetblog.com")
                  }}
                </span>
              </a>
            </li>
            
          </ul>
        </div>

        
      </div>
    </div>
  </footer>
</template>

<script>
import { BIcon } from "bootstrap-vue";
export default {
  comments: { BIcon },
  data() {
    return {};
  },
  created() {},
  methods: {}
};
</script>

<style lang="scss">
footer {
  background-color: $color-dark;
  padding: 70px 0 90px 0;
}
.contact {
  color: $color-grey;
}
.footerContent {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  font-family: $base-font;
  color: $color-grey-light;
}

h6 {
  text-transform: uppercase;
  font-size: 15px;
}

ul li a {
  color: $color-grey;
  letter-spacing: 0.4px;
  line-height: 10px;
  text-decoration: none;
}

ul li a:hover .socialLinkText {
  color: #fff;
  margin-left: 10px;
}
ul li a:hover.AboutUs {
  color: #fff;
  margin-left: 10px;
}

ol,
ul {
  padding: 0;
}

li {
  margin-bottom: 6px;
}

.socialLinkText {
  margin-left: 6px;
  transition: all 0.5s;
}

.socialLinkText:hover {
  color: #fff;
  margin-left: 10px;
  transition: all 0.5s;
}
.AboutUs {
  // margin-left: 6px;
  transition: all 0.5s;
}

.AboutUs:hover {
  color: #fff;
  margin-left: 10px;
  transition: all 0.5s;
}

// ========Mobile media ========
@media screen and (max-width: 768px) {
  .footerContent {
    grid-template-columns: 1fr;
    text-align: left;
    &__logo {
      margin-bottom: 16px;
    }
  }
  s h6 {
    font-size: 14px;
    margin-top: 20px;
  }

  ul li a {
    font-size: 13px;
  }
   .footerContent .footer__top{
     margin-top: 10px;
   }
}
</style>
