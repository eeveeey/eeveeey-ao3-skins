# AO3 Interactive Trifold Letter & Envelope Work Skin Guide

A comprehensive guide and documentation for implementing and customizing the **Trifold Letter & Envelope CSS Work Skin** on Archive of Our Own (AO3). This layout features interactive hover-to-open trifold envelopes, vintage paper styling, custom scrollbars, integrated images, and blurred static envelopes.

---

## Table of Contents
1. [Overview & Features](#overview--features)
2. [How to Install on AO3](#how-to-install-on-ao3)
3. [CSS Architecture & Styling Breakdown](#css-architecture--styling-breakdown)
4. [HTML Snippets & Templates](#html-snippets--templates)
    - [1. Single Letter](#1-single-letter)
    - [2. Integrated Image Letter](#2-integrated-image-letter)
    - [3. Multiple Letters](#3-multiple-letters)
    - [4. Static Envelope](#4-static-envelope)
5. [Customization Guide](#customization-guide)

---

## Overview & Features

* **Interactive Trifold Letters:** Letters slide out and unfold on mouse hover (`:hover`), transitioning smoothly from a sealed envelope view into an extended multi-panel parchment letter.
* **Custom Vintage Styling:** Realistic gradients (`linear-gradient`) mimicking aged parchment, delicate borders, shadows, and custom-styled webkit scrollbars.
* **Envelope Flaps & Stamps:** Includes pre-styled cover areas featuring sender/recipient addresses and custom stamp image support via Pinterest/image URLs.
* **Integrated Images:** Seamlessly embed artwork or photographs that expand alongside the unfolding letter panels.
* **Static Envelope Option:** Perfect for header displays or locked view content using blur filters (`.blur_text`).

---

## How to Install on AO3

1. Log into your AO3 account and navigate to your dashboard (`My Dashboard > Skins`).
2. Click on **Create Work Skin**.
3. Give your skin a descriptive title (e.g., `Vintage Trifold Letter Skin`).
4. Copy the entire CSS block provided below and paste it into the **CSS** text box.
5. Click **Submit**. When posting or editing your work, check the **Work Skin** box and select your newly created skin from the dropdown list.

---

## CSS Code

```css
#workskin body {
  background: #2a2a2a;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 40px 20px;
}

#workskin #chapter-3 {
  overflow: hidden;
  width: 100%;
  max-width: 820px;
  margin: 0 auto;
  padding: 30px 10px;
  background: transparent;
  position: relative;
}

#workskin .trifold_letter {
  flex-direction: column;
  position: relative;
  margin: 0 auto;
  font-size: 0;
  font-family: "Bradley Hand", "Segoe Script", Palatino, serif;
  width: 600px;
  height: 240px;
  max-width: 660px;
  min-width: 50%;
  transition: 2s;
  transition-delay: 2s;
}

#workskin .trifold_static {
  flex-direction: column;
  position: relative;
  margin: 0 auto;
  font-size: 18px !important;
  font-family: "Bradley Hand", "Segoe Script", Palatino, serif;
  width: 600px;
  height: 240px;
  max-width: 660px;
  min-width: 50%;
}

#workskin .blur_text {
  color: black;
  filter: blur(2px);
}

#workskin .trifold_letter:hover {
  height: 600px;
  transition: 2s;
}

#workskin .letter_cover {
  position: absolute;
  top: -20px;
  left: -20px;
  color: #383C45;
  background: linear-gradient(344deg, rgba(255, 254, 242, 1) 0%, rgba(248, 246, 224, 1) 6%, rgba(244, 241, 215, 1) 37%, rgba(238, 235, 203, 1) 51%, rgba(247, 245, 222, 1) 92%, rgba(255, 254, 242, 1) 100%);
  box-shadow: -2px 1px 5px 1px #00000010, 1px -2px 5px 1px #00000010;
  border: solid #383C4550 1px;
  width: 110%;
  min-height: 240px;
  max-height: 240px;
  transition: 2s;
  transition-delay: 2s;
  z-index: 8;
}

#workskin .letter_cover:hover {
  cursor: wait;
}

#workskin .trifold_letter:hover .letter_cover {
  top: -100px;
  left: 0px;
  background: linear-gradient(344deg, rgba(254, 252, 231, 1) 0%, rgba(251, 249, 226, 1) 6%, rgba(244, 241, 215, 1) 37%, rgba(236, 232, 195, 1) 51%, rgba(249, 246, 213, 1) 92%, rgba(255, 253, 225, 1) 100%);
  transform: rotate(15deg);
  transition: 2s;
  z-index: 0;
}

#workskin .letter_cover_text {
  position: relative;
  margin: 0 auto;
  top: 6ch;
  max-width: 60%;
  min-width: 30%;
  font-size: 18px !important;
  overflow: visible;
}

#workskin .letter_cover_text_top {
  position: absolute;
  top: 10px;
  left: 20px;
  max-width: 33%;
  min-width: 30%;
  font-size: 12px !important;
  overflow: visible;
}

#workskin .letter_cover_stamp {
  position: absolute;
  top: 12px;
  right: 12px;
  height: 75px;
  width: 80px;
  min-width: 10%;
  max-width: 30%;
  background: #fffef2;
  background-image: url(https://i.pinimg.com/736x/ca/f8/28/caf828b4a7a3405a51045b6c62202225.jpg);
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center center;
  border-radius: 3px;
  box-shadow: 1px .5px 0px 0px #00000020, 1px .5px 0px 0px white inset;
}

#workskin .letter_top {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  color: #383C45;
  background: linear-gradient(176deg, rgba(255, 251, 240, 1) 0%, rgba(245, 235, 207, 1) 81%, rgba(255, 248, 228, 1) 100%);
  height: 200px;
  border-left: solid #383C4550 1px;
  border-right: solid #383C4550 1px;
  border-top: solid #383C4550 1px;
  border-top-right-radius: 4px;
  border-top-left-radius: 4px;
  box-shadow: -5px -3px 10px 1px #00000010;
  transition: 2s;
  transition-delay: 2s;
  z-index: 7;
}

#workskin .letter_top_text {
  position: relative;
  margin: 0 auto;
  padding-top: 15px;
  height: 100%;
  max-width: 90%;
  font-size: 22px;
  overflow: hidden;
}

#workskin .trifold_letter:hover .letter_top {
  top: 0;
  left: -20px;
  transform: skew(5deg);
  transition: 2s;
}

#workskin .img_container img {
  width: 100%;
  height: 200px;
  opacity: 0.7;
}

#workskin .trifold_letter:hover .img_container,
#workskin .trifold_letter2:hover .img_container {
  top: -50px;
  left: -80px;
  transition: 0.5s;
  transform: skew(-2deg);
  filter: blur(0);
  width: 100%;
  height: 660px;
}

#workskin .trifold_letter:hover .img_container img,
#workskin .trifold_letter2:hover .img_container img {
  filter: blur(0);
  transition: 0.5s;
  transform: skew(-2deg);
  width: 100%;
  height: 660px;
  opacity: 1;
  background-size: cover;
}

#workskin .letter_mid {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  color: #383C45;
  background: linear-gradient(169deg, rgba(214, 205, 179, 1) 0%, rgba(233, 224, 197, 1) 52%, rgba(255, 248, 229, 1) 100%);
  height: 200px;
  box-shadow: -5px -3px 10px 1px #00000010;
  border-left: solid #383C4550 1px;
  border-right: solid #383C4550 1px;
  transition: 2s;
  transition-delay: 2s;
  z-index: 6;
}

#workskin .letter_mid_text {
  position: relative;
  margin: 0 auto;
  padding-top: 25px;
  max-width: 90%;
  height: 100%;
  font-size: 22px;
  overflow: hidden;
}

#workskin .trifold_letter:hover .letter_mid {
  top: 198px;
  left: -20px;
  transform: skew(-5deg);
  transition: 2s;
}

#workskin .letter_bot {
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  color: #383C45;
  background: linear-gradient(353deg, rgba(255, 251, 240, 1) 0%, rgba(242, 231, 201, 1) 79%, rgba(255, 248, 228, 1) 100%);
  height: 200px;
  border-bottom-right-radius: 4px;
  border-bottom-left-radius: 4px;
  border-left: solid #383C4550 1px;
  border-right: solid #383C4550 1px;
  border-bottom: solid #383C4550 1px;
  box-shadow: -5px -3px 10px 1px #00000010;
  transition: 2s;
  transition-delay: 2s;
  z-index: 5;
}

#workskin .letter_bot_text {
  position: relative;
  margin: 0 auto;
  padding-top: 25px;
  max-width: 90%;
  height: 100%;
  font-size: 22px;
  overflow: hidden;
}

#workskin .trifold_letter:hover .letter_bot {
  top: 396px;
  left: -20px;
  transition: 2s;
  transform: skew(5deg);
}

#workskin .trifold_letter2 {
  font-family: 'Bradley Hand', 'Segoe Script', Palatino, serif;
  position: relative;
  margin: 40px auto 0 auto;
  width: 600px;
  height: 240px;
  max-width: 95%;
  min-width: 80%;
  font-size: 0;
  transition: height 2s ease;
}

#workskin .trifold_letter2:hover {
  height: 600px;
}

#workskin .trifold_letter2:hover .letter_top2 {
  height: 660px;
  left: 30px !important;
  top: -20px !important;
  transition: 1s !important;
  z-index: 11;
}

#workskin .trifold_letter2:hover .img_container {
  height: 660px;
  left: 60px !important;
  top: -40px !important;
  transition: 1s !important;
  transform: skew(2deg);
  z-index: 11;
}

#workskin .trifold_letter2:hover .letter_mid2 {
  left: 30px !important;
  top: 180px !important;
  transition: .5s !important;
  z-index: 10;
}

#workskin .trifold_letter2:hover .letter_bot2 {
  left: 30px !important;
  top: 380px !important;
  transition: .5s !important;
  z-index: 9;
}

#workskin .letter_top2 {
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 200px;
  color: #383C45;
  background: linear-gradient(176deg, rgba(255, 251, 240, 1) 0%, rgba(245, 235, 207, 1) 81%, rgba(255, 248, 228, 1) 100%);
  border: solid #383C4550 1px;
  border-radius: 4px 4px 0 0;
  box-shadow: -5px -3px 10px 1px #00000010;
  transition: all 2s ease;
  z-index: 4;
}

#workskin .img_container {
  position: absolute;
  width: 100%;
  left: 0;
  top: 0px;
  color: #383C45;
  background: linear-gradient(176deg, rgba(198, 189, 165, 1) 0%, rgba(176, 159, 111, 1) 81%, rgba(228, 205, 140, 1) 100%);
  height: 200px;
  max-width: 80%;
  border-left: solid #383C4550 1px;
  border-right: solid #383C4550 1px;
  border-top: solid #383C4550 1px;
  border-top-right-radius: 4px;
  border-top-left-radius: 4px;
  box-shadow: -5px -3px 10px 1px #00000010;
  transition: 2s;
  transition-delay: 2s;
  z-index: 4;
}

#workskin .letter_top_text2,
#workskin .letter_mid_text2,
#workskin .letter_bot_text2 {
  position: relative;
  margin: 0 auto;
  max-width: 90%;
  height: 170px;
  overflow: auto;
  padding-top: 15px;
}

#workskin .letter_mid2 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 200px;
  color: #383C45;
  background: linear-gradient(169deg, rgba(214, 205, 179, 1) 0%, rgba(233, 224, 197, 1) 52%, rgba(255, 248, 229, 1) 100%);
  border-left: solid #383C4550 1px;
  border-right: solid #383C4550 1px;
  box-shadow: -5px -3px 10px 1px #00000010;
  transition: all 2s ease;
  z-index: 3;
}

#workskin .letter_bot2 {
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 200px;
  color: #383C45;
  background: linear-gradient(353deg, rgba(255, 251, 240, 1) 0%, rgba(242, 231, 201, 1) 79%, rgba(255, 248, 228, 1) 100%);
  border: solid #383C4550 1px;
  border-radius: 0 0 4px 4px;
  box-shadow: -5px -3px 10px 1px #00000010;
  transition: all 2s ease;
  z-index: 2;
}

/* Custom Scrollbars */
#workskin .letter_bot_text::-webkit-scrollbar,
#workskin .letter_mid_text::-webkit-scrollbar,
#workskin .letter_top_text::-webkit-scrollbar,
#workskin .letter_bot_text2::-webkit-scrollbar,
#workskin .letter_mid_text2::-webkit-scrollbar,
#workskin .letter_top_text2::-webkit-scrollbar {
  -webkit-appearance: none;
  display: block;
  width: 8px;
}

#workskin .letter_bot_text::-webkit-scrollbar-thumb,
#workskin .letter_mid_text::-webkit-scrollbar-thumb,
#workskin .letter_top_text::-webkit-scrollbar-thumb,
#workskin .letter_bot_text2::-webkit-scrollbar-thumb,
#workskin .letter_mid_text2::-webkit-scrollbar-thumb,
#workskin .letter_top_text2::-webkit-scrollbar-thumb {
  background: linear-gradient(180deg, rgba(134, 156, 149, 0) 0%, rgba(187, 207, 200, 1) 48%, rgba(134, 156, 149, 0) 100%);
  border-radius: 8px;
  border: 2px solid #ffffff25;
}

#workskin .letter_bot_text::-webkit-scrollbar-thumb:hover,
#workskin .letter_mid_text::-webkit-scrollbar-thumb:hover,
#workskin .letter_top_text::-webkit-scrollbar-thumb:hover,
#workskin .letter_bot_text2::-webkit-scrollbar-thumb:hover,
#workskin .letter_mid_text2::-webkit-scrollbar-thumb:hover,
#workskin .letter_top_text2::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(180deg, rgba(134, 156, 149, 0) 0%, rgba(140, 154, 149, 1) 48%, rgba(134, 156, 149, 0) 100%);
}

#workskin .letter_bot_text::-webkit-scrollbar-track,
#workskin .letter_mid_text::-webkit-scrollbar-track,
#workskin .letter_top_text::-webkit-scrollbar-track,
#workskin .letter_bot_text2::-webkit-scrollbar-track,
#workskin .letter_mid_text2::-webkit-scrollbar-track,
#workskin .letter_top_text2::-webkit-scrollbar-track {
  border-radius: 8px;
  background-color: #ffffff25;
}

#workskin .letter_bot_text,
#workskin .letter_mid_text,
#workskin .letter_top_text,
#workskin .letter_bot_text2,
#workskin .letter_mid_text2,
#workskin .letter_top_text2 {
  scrollbar-width: thin;
  scrollbar-color: #bbc8c8 #ffffff25;
  font-size: 12px;
}

#workskin .trifold_letter,
#workskin .trifold_letter2 {
  max-width: 95%;
  min-width: 80%;
}

#workskin .hidden_element {
  display: none;
}
```

---

## HTML Snippets & Templates

When posting your work on AO3, ensure your work editor is set to **HTML** mode before pasting the templates below. Replace placeholders like `{SENDER_NAME}`, `{RECIPIENT_NAME}`, `{DATE}`, and content variables with your text.

### 1. Single Letter
```html
<h1>Single Letter</h1>

<div class="trifold_letter">
        <div class="letter_cover">
                <div class="letter_cover_flap">
                        <div class="letter_cover_flap2"></div>
                </div>
                <div class="letter_cover_stamp"></div>
                <div class="letter_cover_text_top">
                        <p><b>{SENDER_NAME}</b><br />
                                {SENDER_ADDRESS}<br />
                        </p>
                </div>
                <div class="letter_cover_text">
                        <p align="center"><b>{RECIPIENT_NAME}</b><br />
                                {RECIPIENT_ADDRESS}<br />
                        </p>
                </div>
        </div>
        <div class="letter_top">
                <div class="letter_top_text">
                        <p>{DATE}</p>
                        <p>Dear {RECIPIENT_NAME},</p>
                        <p>{TOP_CONTENT}</p>
                </div>
        </div>
        <div class="letter_mid">
                <div class="letter_mid_text">
                        <p>{MIDDLE_CONTENT}</p>
                </div>
        </div>
        <div class="letter_bot">
                <div class="letter_bot_text">
                        <p>{BOTTOM_CONTENT}</p>
                        <p align="right"><em>Best Regards,</em></p>
                        <p align="right"><em>{SENDER_NAME}</em></p>
                </div>
        </div>
</div>
```

### 2. Integrated Image Letter
```html
<h1>Integrated Image Letter</h1>

<div class="trifold_letter">
        <div class="letter_cover">
                <div class="letter_cover_flap">
                        <div class="letter_cover_flap2"></div>
                </div>
                <div class="letter_cover_stamp"></div>
                <div class="letter_cover_text_top">
                        <p><b>{SENDER_NAME}</b><br />
                                {SENDER_ADDRESS}<br />
                        </p>
                </div>
                <div class="letter_cover_text">
                        <p align="center"><b>{RECIPIENT_NAME}</b><br />
                                {RECIPIENT_ADDRESS}<br />
                                c/o Dr. A. Bloom</p>
                </div>
        </div>
        <div class="letter_top">
                <div class="letter_top_text">
                        <p><b>{DATE}</b></p>
                        <p><b>My Dear {RECIPIENT_NAME},</b></p>
                        <p><em>{TOP_CONTENT}</em></p>
                </div>
        </div>
        <div class="letter_mid">
                <div class="letter_mid_text">
                        <p><em>{MIDDLE_CONTENT}</em></p>
                </div>
        </div>
        <div class="letter_bot">
                <div class="letter_bot_text">
                        <p><em>{BOTTOM_CONTENT}</em></p>
                        <p align="right"><em>{SENDER_NAME}</em></p>
                </div>
        </div>
        <div class="trifold_letter2">
                <div class="img_container">
                        <p><img class="letter_top_img2"
                                        src="https://i.pinimg.com/1200x/b6/af/9a/b6af9af0f062ac084c76597d28034737.jpg"
                                        alt="Top Image"></p>
                </div>
        </div>
</div>
```

### 3. Multiple Letters
```html
<h1>Multiple Letters</h1>

<div class="trifold_letter">
        <div class="letter_cover">
                <div class="letter_cover_flap">
                        <div class="letter_cover_flap2"></div>
                </div>
                <div class="letter_cover_stamp"></div>
                <div class="letter_cover_text_top">
                        <p><b>{SENDER_NAME}</b><br />
                                {SENDER_ADDRESS}
                        </p>
                </div>
                <div class="letter_cover_text">
                        <p align="center"><b>{RECIPIENT_NAME}</b><br />
                                {RECIPIENT_ADDRESS}<br />
                                c/o Dr. A. Bloom</p>
                </div>
        </div>
        <div class="letter_top">
                <div class="letter_top_text">
                        <p><b>DATE</b></p>
                        <p><b>Dear {RECIPIENT_NAME},</b></p>
                        <p>{TOP_TEXT}</p>
                </div>
        </div>
        <div class="letter_mid">
                <div class="letter_mid_text">
                        <p>{MIDDLE_TEXT}</p>
                </div>
        </div>
        <div class="letter_bot">
                <div class="letter_bot_text">
                        <p>{BOTTOM_TEXT}</p>
                </div>
        </div>
        <div class="trifold_letter2">
                <div class="letter_top2">
                        <p>{TOP_TEXT2}</p>
                </div>
                <div class="letter_mid2">
                        <div class="letter_mid_text2">
                                <p><em>{MIDDLE_TEXT2}</em></p>
                        </div>
                </div>
                <div class="letter_bot2">
                        <div class="letter_bot_text2">
                                <p><em>{BOTTOM_TEXT2}</em></p>
                                <p align="right"><em>{SIGNATURE}</em></p>
                        </div>
                </div>
        </div>
</div>
```

### 4. Static Envelope
```html
<h1>Static Envelope</h1>

<div class="trifold_static">
        <div class="letter_cover">
                <div class="letter_cover_flap">
                        <div class="letter_cover_flap2"></div>
                </div>
                <div class="letter_cover_stamp"></div>
                <div class="letter_cover_text_top">
                        <p><b>{SENDER_NAME}</b><br />
                                {SENDER_ADDRESS}
                        </p>
                </div>
                <div class="letter_cover_text blur_text">
                        <p align="center"><b>{RECIPIENT_NAME}</b><br />
                                {RECIPIENT_ADDRESS}<br /></p>
                </div>
        </div>
</div>
```

---

## Customization Guide

* **Fonts:** Modify the font family by changing `"Bradley Hand", "Segoe Script", Palatino, serif` in `.trifold_letter` and `.trifold_static`.
* **Envelope Stamp:** Update the stamp image by changing the `background-image` URL under `#workskin .letter_cover_stamp`.
* **Animation Speed:** Adjust the `transition: 2s` property across `.trifold_letter`, `.letter_cover`, `.letter_top`, etc., to make the unfolding animation faster or slower.
* **Scrollable Content:** Each section (`letter_top_text`, `letter_mid_text`, etc.) includes `overflow: auto` and custom scrollbars so lengthy paragraphs remain neat without breaking the container layout.
