<template>
  <div class="banner">
    <div class="home-banners">
      <div class="row-full-width-inner" data-element="inner">
        <div
          data-content-type="html"
          data-appearance="default"
          data-element="main"
          data-decoded="true"
        >
          <div class="home-banners__item">
            <picture>
              <source
                srcset="
                  https://clickfashion.pl/media/idea07_contenttypes/contenttypeentity/image/b/a/baner_08-04_1.png
                "
                media="(max-width: 639.98px)"
              />
              <img
                src="https://clickfashion.pl/media/idea07_contenttypes/contenttypeentity/image/b/a/baner_08-04.png"
                alt="CLICK FASHION"
              />
            </picture>

            <div class="home-banners__content-wrapper">
              <div class="home-banners__content">
                <p class="banner__category">
                  Kolekcja 2024 / MODOWE INSPIRACJE
                </p>
                <p class="banner__title">CLICK FASHION</p>
                <div class="banner__content">
                  <p>
                    Ręcznie robione ubrania, naturalne materiały, polska marka
                  </p>
                </div>
                <a
                  class="banner__link"
                  href="https://clickfashion.pl/nowosci.html"
                  tabindex="0"
                >
                  WIĘCEJ NOWOŚCI
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="home-banners__arrows arrows-container"></div>
      <div
        class="homepage-slider__thumb"
        style="width: 100%; display: inline-block"
      >
        <span class="slide-number"></span>
        <img
          src="https://clickfashion.pl/media/idea07_contenttypes/contenttypeentity/image/b/a/baner_08-04.png"
          alt=""
        />
      </div>
      <div
        data-content-type="html"
        data-appearance="default"
        data-element="main"
        data-decoded="true"
      >
        <div class="socials-box">
          <p class="socials-box__text">Social media</p>
          <ul class="socials-box__links">
            <li class="socials-box__link facebook">
              <a
                title="Facebook"
                href="https://www.facebook.com/ClickFashion.polska/"
              >
                <img
                  src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHg9IjBweCIgeT0iMHB4IiB3aWR0aD0iNTAiIGhlaWdodD0iNTAiIHZpZXdCb3g9IjAgMCA1MCA1MCI+CjxwYXRoIGQ9Ik0gOSA0IEMgNi4yNTA0ODM5IDQgNCA2LjI1MDQ4MzkgNCA5IEwgNCA0MSBDIDQgNDMuNzQ5NTE2IDYuMjUwNDgzOSA0NiA5IDQ2IEwgMjUuODMyMDMxIDQ2IEEgMS4wMDAxIDEuMDAwMSAwIDAgMCAyNi4xNTgyMDMgNDYgTCAzMS44MzIwMzEgNDYgQSAxLjAwMDEgMS4wMDAxIDAgMCAwIDMyLjE1ODIwMyA0NiBMIDQxIDQ2IEMgNDMuNzQ5NTE2IDQ2IDQ2IDQzLjc0OTUxNiA0NiA0MSBMIDQ2IDkgQyA0NiA2LjI1MDQ4MzkgNDMuNzQ5NTE2IDQgNDEgNCBMIDkgNCB6IE0gOSA2IEwgNDEgNiBDIDQyLjY2ODQ4NCA2IDQ0IDcuMzMxNTE2MSA0NCA5IEwgNDQgNDEgQyA0NCA0Mi42Njg0ODQgNDIuNjY4NDg0IDQ0IDQxIDQ0IEwgMzMgNDQgTCAzMyAzMCBMIDM2LjgyMDMxMiAzMCBMIDM4LjIyMDcwMyAyMyBMIDMzIDIzIEwgMzMgMjEgQyAzMyAyMC40NDI1MDggMzMuMDUzMDUgMjAuMzk4OTI5IDMzLjI0MDIzNCAyMC4yNzczNDQgQyAzMy40Mjc0MTkgMjAuMTU1NzU4IDM0LjAwNTgyMiAyMCAzNSAyMCBMIDM4IDIwIEwgMzggMTQuMzY5MTQxIEwgMzcuNDI5Njg4IDE0LjA5NzY1NiBDIDM3LjQyOTY4OCAxNC4wOTc2NTYgMzUuMTMyNjQ3IDEzIDMyIDEzIEMgMjkuNzUgMTMgMjcuOTAxNTg4IDEzLjg5NjQ1MyAyNi43MTg3NSAxNS4zNzUgQyAyNS41MzU5MTIgMTYuODUzNTQ3IDI1IDE4LjgzMzMzMyAyNSAyMSBMIDI1IDIzIEwgMjIgMjMgTCAyMiAzMCBMIDI1IDMwIEwgMjUgNDQgTCA5IDQ0IEMgNy4zMzE1MTYxIDQ0IDYgNDIuNjY4NDg0IDYgNDEgTCA2IDkgQyA2IDcuMzMxNTE2MSA3LjMzMTUxNjEgNiA5IDYgeiBNIDMyIDE1IEMgMzQuMDc5MDYyIDE1IDM1LjM4NzM2IDE1LjQ1ODQ1NSAzNiAxNS43MDExNzIgTCAzNiAxOCBMIDM1IDE4IEMgMzMuODQ5MTc4IDE4IDMyLjkyNjk1NiAxOC4wOTUyIDMyLjE1MDM5MSAxOC41OTk2MDkgQyAzMS4zNzM4MjYgMTkuMTA0MDI0IDMxIDIwLjA2MTQ5MiAzMSAyMSBMIDMxIDI1IEwgMzUuNzc5Mjk3IDI1IEwgMzUuMTc5Njg4IDI4IEwgMzEgMjggTCAzMSA0NCBMIDI3IDQ0IEwgMjcgMjggTCAyNCAyOCBMIDI0IDI1IEwgMjcgMjUgTCAyNyAyMSBDIDI3IDE5LjE2NjY2NyAyNy40NjQwODggMTcuNjQ2NDUzIDI4LjI4MTI1IDE2LjYyNSBDIDI5LjA5ODQxMiAxNS42MDM1NDcgMzAuMjUgMTUgMzIgMTUgeiI+PC9wYXRoPgo8L3N2Zz4="
                  alt="Facebook"
                  width="24"
                  height="24"
                />
              </a>
            </li>
            <li class="socials-box__link instagram">
              <a
                title="Instagram"
                href="https://www.instagram.com/clickfashionpolska/"
              >
                <img
                  src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHg9IjBweCIgeT0iMHB4IiB3aWR0aD0iNTAiIGhlaWdodD0iNTAiIHZpZXdCb3g9IjAgMCA1MCA1MCI+CjxwYXRoIGQ9Ik0gMTYgMyBDIDguODMyNDgzOSAzIDMgOC44MzI0ODM5IDMgMTYgTCAzIDM0IEMgMyA0MS4xNjc1MTYgOC44MzI0ODM5IDQ3IDE2IDQ3IEwgMzQgNDcgQyA0MS4xNjc1MTYgNDcgNDcgNDEuMTY3NTE2IDQ3IDM0IEwgNDcgMTYgQyA0NyA4LjgzMjQ4MzkgNDEuMTY3NTE2IDMgMzQgMyBMIDE2IDMgeiBNIDE2IDUgTCAzNCA1IEMgNDAuMDg2NDg0IDUgNDUgOS45MTM1MTYxIDQ1IDE2IEwgNDUgMzQgQyA0NSA0MC4wODY0ODQgNDAuMDg2NDg0IDQ1IDM0IDQ1IEwgMTYgNDUgQyA5LjkxMzUxNjEgNDUgNSA0MC4wODY0ODQgNSAzNCBMIDUgMTYgQyA1IDkuOTEzNTE2MSA5LjkxMzUxNjEgNSAxNiA1IHogTSAzNyAxMSBBIDIgMiAwIDAgMCAzNSAxMyBBIDIgMiAwIDAgMCAzNyAxNSBBIDIgMiAwIDAgMCAzOSAxMyBBIDIgMiAwIDAgMCAzNyAxMSB6IE0gMjUgMTQgQyAxOC45MzY3MTIgMTQgMTQgMTguOTM2NzEyIDE0IDI1IEMgMTQgMzEuMDYzMjg4IDE4LjkzNjcxMiAzNiAyNSAzNiBDIDMxLjA2MzI4OCAzNiAzNiAzMS4wNjMyODggMzYgMjUgQyAzNiAxOC45MzY3MTIgMzEuMDYzMjg4IDE0IDI1IDE0IHogTSAyNSAxNiBDIDI5Ljk4MjQwNyAxNiAzNCAyMC4wMTc1OTMgMzQgMjUgQyAzNCAyOS45ODI0MDcgMjkuOTgyNDA3IDM0IDI1IDM0IEMgMjAuMDE3NTkzIDM0IDE2IDI5Ljk4MjQwNyAxNiAyNSBDIDE2IDIwLjAxNzU5MyAyMC4wMTc1OTMgMTYgMjUgMTYgeiI+PC9wYXRoPgo8L3N2Zz4="
                  alt="Instagram"
                  width="24"
                  height="24"
                />
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeBanners",
};
</script>

<style scoped>
.banner {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #000;
  box-sizing: border-box;
  justify-content: flex-start;
  display: flex;
  flex-direction: column;
  background-position: left top;
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: scroll;
}
.row-full-width-inner {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #000;
  box-sizing: border-box;
  margin-left: auto;
  margin-right: auto;
  width: 100%;
  max-width: 100%;
}
.home-banners {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #000;
  word-wrap: break-word;
  box-sizing: border-box;
  margin: 0 auto;
  position: relative;
  max-width: 1920px;
}
.home-banners__item {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #000;
  word-wrap: break-word;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  box-sizing: border-box;
  position: relative;
  width: 100%;
  display: inline-block;
}
.home-banners__picture {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #000;
  word-wrap: break-word;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  box-sizing: border-box;
  max-width: 100%;
  width: 100%;
  display: block;
  height: auto;
  margin: 0 auto;
  position: relative;
  max-height: 700px;
  min-height: 700px;
}
.home-banners__content {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  word-wrap: break-word;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  box-sizing: border-box;
  color: #fff;
  align-self: center;
  max-width: 70%;
  margin-top: 80px;
}
.home-banners__content-wrapper {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #000;
  word-wrap: break-word;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  box-sizing: border-box;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 2;
  margin: 0 auto;
  display: flex;
  padding-right: 15px;
  padding-left: 15px;
  max-width: 1600px;
}
.banner__category {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-family: "Montserrat", sans-serif;
  word-wrap: break-word;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  color: #fff;
  box-sizing: border-box;
  margin-top: 0;
  letter-spacing: 0.166666em;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  max-width: 540px;
  margin-bottom: 8px;
}
.banner__title {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-family: "Montserrat", sans-serif;
  word-wrap: break-word;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  color: #fff;
  box-sizing: border-box;
  margin-top: 0;
  line-height: 1.2;
  margin-bottom: 1.6rem;
  max-width: 250px;
  font-weight: 600;
  letter-spacing: normal;
  font-size: 3rem;
}
.banner__content {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  word-wrap: break-word;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  box-sizing: border-box;
  color: #fff;
  max-width: 60%;
  font-family: "Merriweather", serif;
  line-height: 1.733333;
  margin-bottom: 1.6em;
}
.banner__link {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  word-wrap: break-word;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  box-sizing: border-box;
  display: flex;
  align-items: center;
  justify-content: space-between;
  -webkit-transition: all 0.3s ease-in-out;
  min-height: 36px;
  font-size: 11px;
  letter-spacing: 1.83px;
  background: #000;
  border: 1px solid;
  border-color: #000;
  text-transform: uppercase;
  font-weight: 700;
  border-radius: 0;
  padding: 0 20px;
  min-width: 190px;
  box-shadow: none;
  width: 190px;
  padding-right: 18px;
  text-decoration: none;
  color: #fff;
}
.socials-box {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #000;
  word-wrap: break-word;
  box-sizing: border-box;
  background: #fff;
  padding: 172px 0 25px;
  z-index: 50;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 0;
  position: absolute;
  right: 0;
  top: 0;
  left: unset;
  text-align: right;
  width: auto;
  padding-right: 25px;
  padding-left: 25px;
}
.socials-box__text {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  font-family: "Montserrat", sans-serif;
  word-wrap: break-word;
  text-align: right;
  box-sizing: border-box;
  letter-spacing: 2.2px;
  opacity: 0.5;
  color: #000;
  line-height: 1.2;
  transform: rotate(90deg);
  transform-origin: 50% 50%;
  text-transform: uppercase;
  white-space: nowrap;
  margin: 0;
  position: absolute;
  top: 97px;
}
.socials-box__links {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #fff;
  word-wrap: break-word;
  text-align: right;
  box-sizing: border-box;
  list-style: none;
  display: flex;
  flex-direction: column;
  padding: 0;
  margin: 0;
}
.socials-box__link facebook {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #fff;
  word-wrap: break-word;
  list-style: none;
  box-sizing: border-box;
  margin: 20px 0;
  display: inline-block;
}
.socials-box__link instagram {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #fff;
  word-wrap: break-word;
  list-style: none;
  box-sizing: border-box;
  margin: 20px 0;
  display: inline-block;
}
svg {
  fill: #fff; /* White fill */
  stroke: #000;
  stroke-width: 2;
}
.homepage-slider__thumb {
  position: absolute;
  bottom: 0;
  width: 100%;
  display: block;
  height: 240px;
}

.homepage-slider__thumb .slide-number {
  position: absolute;
  top: 10px;
  left: 10px;
  color: #fff;
  z-index: 2;
}

.homepage-slider__thumb img {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(105%);
  width: 240px;
  height: 159.58px;
  object-fit: cover;
}
.home-banners__arrows {
  -webkit-text-size-adjust: 100%;
  font-style: normal;
  font-weight: 400;
  line-height: 1.42857143;
  font-family: "Montserrat", sans-serif;
  font-size: 12px;
  color: #000;
  word-wrap: break-word;
  box-sizing: border-box;
  position: absolute;
  opacity: 1;
  z-index: 5;
  -webkit-transition: opacity 0.3s ease-in-out;
  bottom: -4px;
  left: 0;
  background-color: #fff;
  width: 26.6%;
  padding: 12px;
  display: flex;
  justify-content: flex-end;
  align-content: center;
  height: 112px;
}
</style>
