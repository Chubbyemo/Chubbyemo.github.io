---
layout: page
title: art
permalink: /art/
description: Drawings, stickers, and small visual experiments.
nav: true
nav_order: 2
---

<style>
  .art-intro {
    max-width: 720px;
    margin: 0 auto 1.75rem;
    color: var(--global-text-color-light);
    font-size: 0.98rem;
    line-height: 1.7;
  }

  .art-filters {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 0.45rem;
    margin: 0 0 1.35rem;
  }

  .art-filter {
    border: 1px solid var(--global-divider-color);
    border-radius: 999px;
    background: var(--global-bg-color);
    color: var(--global-text-color);
    padding: 0.34rem 0.76rem;
    font: inherit;
    font-size: 0.86rem;
    line-height: 1;
    cursor: pointer;
    transition:
      background 160ms ease,
      border-color 160ms ease,
      color 160ms ease,
      transform 160ms ease;
  }

  .art-filter:hover,
  .art-filter:focus-visible,
  .art-filter.is-active {
    border-color: var(--global-theme-color);
    color: var(--global-theme-color);
    transform: translateY(-1px);
  }

  .art-cloud {
    position: relative;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    gap: clamp(0.45rem, 1.8vw, 1.05rem);
    max-width: 1080px;
    margin: 0 auto;
    padding: clamp(0.6rem, 2vw, 1.2rem) 0 clamp(1rem, 3vw, 2rem);
  }

  .art-piece {
    --size: 118px;
    --rotate: 0deg;
    --delay: 0s;
    --drift: 12px;
    width: clamp(74px, var(--size), 230px);
    aspect-ratio: 1;
    border: 0;
    border-radius: 7px;
    background:
      linear-gradient(135deg, rgba(255, 255, 255, 0.72), rgba(245, 247, 250, 0.45)),
      var(--global-bg-color);
    box-shadow: 0 10px 26px rgba(0, 0, 0, 0.08);
    cursor: zoom-in;
    padding: 0.42rem;
    transform: rotate(var(--rotate));
    animation: art-drift 6.5s ease-in-out infinite;
    animation-delay: var(--delay);
    transition:
      box-shadow 180ms ease,
      opacity 180ms ease,
      transform 180ms ease;
  }

  .art-piece.is-hidden {
    display: none;
  }

  .art-piece:hover,
  .art-piece:focus-visible {
    z-index: 3;
    box-shadow: 0 16px 42px rgba(0, 0, 0, 0.16);
    outline: 2px solid var(--global-theme-color);
    outline-offset: 3px;
    transform: rotate(0deg) translateY(-4px) scale(1.08);
    animation-play-state: paused;
  }

  .art-piece img {
    width: 100%;
    height: 100%;
    display: block;
    object-fit: contain;
    pointer-events: none;
  }

  .art-piece[data-kind="painting"] {
    --size: 172px;
    aspect-ratio: 4 / 5;
    padding: 0.35rem;
    background: #f8f6f1;
  }

  .art-piece[data-kind="gif"] {
    --size: 98px;
    background: #f7fbfb;
  }

  .art-piece:nth-of-type(5n) {
    margin-top: 1.2rem;
  }

  .art-piece:nth-of-type(7n) {
    margin-bottom: 1rem;
  }

  .art-piece:nth-of-type(11n) {
    margin-left: 0.9rem;
  }

  @keyframes art-drift {
    0%,
    100% {
      translate: 0 0;
    }
    50% {
      translate: 0 calc(var(--drift) * -1);
    }
  }

  .art-viewer {
    position: fixed;
    inset: 0;
    z-index: 2000;
    display: none;
    align-items: center;
    justify-content: center;
    padding: clamp(1rem, 4vw, 2.5rem);
    background: rgba(16, 18, 22, 0.78);
    backdrop-filter: blur(5px);
  }

  .art-viewer.is-open {
    display: flex;
  }

  .art-viewer__inner {
    position: relative;
    max-width: min(92vw, 980px);
    max-height: 88vh;
  }

  .art-viewer__image {
    display: block;
    max-width: 100%;
    max-height: 82vh;
    object-fit: contain;
    border-radius: 7px;
    background: #f7f7f4;
    box-shadow: 0 22px 80px rgba(0, 0, 0, 0.34);
  }

  .art-viewer__close {
    position: absolute;
    top: -0.8rem;
    right: -0.8rem;
    width: 2.25rem;
    height: 2.25rem;
    border: 1px solid rgba(255, 255, 255, 0.34);
    border-radius: 50%;
    background: rgba(18, 20, 25, 0.86);
    color: #fff;
    font-size: 1.4rem;
    line-height: 1;
    cursor: pointer;
  }

  @media (max-width: 640px) {
    .art-piece {
      --size: 92px;
    }

    .art-piece[data-kind="painting"] {
      --size: 136px;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .art-piece {
      animation: none;
      transition: none;
    }
  }
</style>

<p class="art-intro">
  A small corner for drawings, stickers, and visual experiments. I keep it separate from the research pages so the portfolio stays academic, while still leaving room for the visual side of how I think and make things.
</p>

<div class="art-filters" aria-label="Artwork filters">
  <button class="art-filter is-active" type="button" data-filter="all">all</button>
  <button class="art-filter" type="button" data-filter="painting">paintings</button>
  <button class="art-filter" type="button" data-filter="sticker">stickers</button>
  <button class="art-filter" type="button" data-filter="gif">motion</button>
</div>

<div class="art-cloud" id="art-cloud">
  <button class="art-piece" type="button" data-kind="painting" style="--rotate:-3deg;--delay:-1.2s;--drift:10px"><img src="{{ '/assets/img/art/painting-01.jpg' | relative_url }}" alt="Painting 01"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:104px;--rotate:6deg;--delay:-0.4s"><img src="{{ '/assets/img/art/rat-01.png' | relative_url }}" alt="Sticker 01"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:-8deg;--delay:-2.1s"><img src="{{ '/assets/img/art/coma-01.gif' | relative_url }}" alt="Motion sticker 01"></button>
  <button class="art-piece" type="button" data-kind="painting" style="--rotate:4deg;--delay:-3.1s;--drift:14px"><img src="{{ '/assets/img/art/painting-02.png' | relative_url }}" alt="Painting 02"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:92px;--rotate:-6deg;--delay:-1.7s"><img src="{{ '/assets/img/art/mouse-01.png' | relative_url }}" alt="Sticker 02"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:118px;--rotate:9deg;--delay:-2.8s"><img src="{{ '/assets/img/art/ball-01.png' | relative_url }}" alt="Sticker 03"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:5deg;--delay:-0.8s"><img src="{{ '/assets/img/art/coma-03.gif' | relative_url }}" alt="Motion sticker 02"></button>
  <button class="art-piece" type="button" data-kind="painting" style="--rotate:-5deg;--delay:-2.4s;--drift:16px"><img src="{{ '/assets/img/art/painting-03.png' | relative_url }}" alt="Painting 03"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:108px;--rotate:3deg;--delay:-1.1s"><img src="{{ '/assets/img/art/rat-02.png' | relative_url }}" alt="Sticker 04"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:126px;--rotate:-10deg;--delay:-3.5s"><img src="{{ '/assets/img/art/mouse-02.png' | relative_url }}" alt="Sticker 05"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:8deg;--delay:-1.9s"><img src="{{ '/assets/img/art/coma-05.gif' | relative_url }}" alt="Motion sticker 03"></button>
  <button class="art-piece" type="button" data-kind="painting" style="--rotate:2deg;--delay:-0.6s"><img src="{{ '/assets/img/art/painting-04.png' | relative_url }}" alt="Painting 04"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:96px;--rotate:-4deg;--delay:-2.2s"><img src="{{ '/assets/img/art/rat-03.png' | relative_url }}" alt="Sticker 06"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:110px;--rotate:7deg;--delay:-3.2s"><img src="{{ '/assets/img/art/ball-02.png' | relative_url }}" alt="Sticker 07"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:-7deg;--delay:-0.9s"><img src="{{ '/assets/img/art/coma-07.gif' | relative_url }}" alt="Motion sticker 04"></button>
  <button class="art-piece" type="button" data-kind="painting" style="--rotate:-2deg;--delay:-1.4s;--drift:12px"><img src="{{ '/assets/img/art/painting-05.png' | relative_url }}" alt="Painting 05"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:104px;--rotate:10deg;--delay:-2.6s"><img src="{{ '/assets/img/art/mouse-03.png' | relative_url }}" alt="Sticker 08"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:116px;--rotate:-9deg;--delay:-1.5s"><img src="{{ '/assets/img/art/rat-04.png' | relative_url }}" alt="Sticker 09"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:4deg;--delay:-3.8s"><img src="{{ '/assets/img/art/coma-08.gif' | relative_url }}" alt="Motion sticker 05"></button>
  <button class="art-piece" type="button" data-kind="painting" style="--rotate:5deg;--delay:-2.9s"><img src="{{ '/assets/img/art/painting-06.png' | relative_url }}" alt="Painting 06"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:86px;--rotate:-3deg;--delay:-0.7s"><img src="{{ '/assets/img/art/ball-03.png' | relative_url }}" alt="Sticker 10"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:124px;--rotate:8deg;--delay:-2.5s"><img src="{{ '/assets/img/art/mouse-04.png' | relative_url }}" alt="Sticker 11"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:-5deg;--delay:-1.8s"><img src="{{ '/assets/img/art/coma-09.gif' | relative_url }}" alt="Motion sticker 06"></button>
  <button class="art-piece" type="button" data-kind="painting" style="--rotate:-6deg;--delay:-3.3s"><img src="{{ '/assets/img/art/painting-07.png' | relative_url }}" alt="Painting 07"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:112px;--rotate:2deg;--delay:-0.3s"><img src="{{ '/assets/img/art/rat-05.png' | relative_url }}" alt="Sticker 12"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:104px;--rotate:-8deg;--delay:-2.7s"><img src="{{ '/assets/img/art/ball-04.png' | relative_url }}" alt="Sticker 13"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:9deg;--delay:-1.6s"><img src="{{ '/assets/img/art/coma-11.gif' | relative_url }}" alt="Motion sticker 07"></button>
  <button class="art-piece" type="button" data-kind="painting" style="--rotate:3deg;--delay:-2.3s"><img src="{{ '/assets/img/art/painting-08.png' | relative_url }}" alt="Painting 08"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:88px;--rotate:-11deg;--delay:-4s"><img src="{{ '/assets/img/art/mouse-05.png' | relative_url }}" alt="Sticker 14"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:120px;--rotate:6deg;--delay:-1s"><img src="{{ '/assets/img/art/rat-06.png' | relative_url }}" alt="Sticker 15"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:-2deg;--delay:-3.6s"><img src="{{ '/assets/img/art/coma-12.gif' | relative_url }}" alt="Motion sticker 08"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:96px;--rotate:11deg;--delay:-2s"><img src="{{ '/assets/img/art/ball-05.png' | relative_url }}" alt="Sticker 16"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:126px;--rotate:-4deg;--delay:-0.2s"><img src="{{ '/assets/img/art/mouse-06.png' | relative_url }}" alt="Sticker 17"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:7deg;--delay:-2.8s"><img src="{{ '/assets/img/art/coma-13.gif' | relative_url }}" alt="Motion sticker 09"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:108px;--rotate:-7deg;--delay:-3.4s"><img src="{{ '/assets/img/art/rat-07.png' | relative_url }}" alt="Sticker 18"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:116px;--rotate:4deg;--delay:-1.3s"><img src="{{ '/assets/img/art/mouse-07.png' | relative_url }}" alt="Sticker 19"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:-9deg;--delay:-0.5s"><img src="{{ '/assets/img/art/coma-14.gif' | relative_url }}" alt="Motion sticker 10"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:90px;--rotate:8deg;--delay:-2.1s"><img src="{{ '/assets/img/art/ball-06.png' | relative_url }}" alt="Sticker 20"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:124px;--rotate:-5deg;--delay:-3.7s"><img src="{{ '/assets/img/art/rat-08.png' | relative_url }}" alt="Sticker 21"></button>
  <button class="art-piece" type="button" data-kind="gif" style="--rotate:5deg;--delay:-1.9s"><img src="{{ '/assets/img/art/coma-16.gif' | relative_url }}" alt="Motion sticker 11"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:102px;--rotate:-2deg;--delay:-0.6s"><img src="{{ '/assets/img/art/mouse-08.png' | relative_url }}" alt="Sticker 22"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:112px;--rotate:10deg;--delay:-2.4s"><img src="{{ '/assets/img/art/rat-09.png' | relative_url }}" alt="Sticker 23"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:96px;--rotate:-8deg;--delay:-1.1s"><img src="{{ '/assets/img/art/ball-07.png' | relative_url }}" alt="Sticker 24"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:122px;--rotate:3deg;--delay:-3.1s"><img src="{{ '/assets/img/art/mouse-09.png' | relative_url }}" alt="Sticker 25"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:106px;--rotate:-6deg;--delay:-2.9s"><img src="{{ '/assets/img/art/rat-10.png' | relative_url }}" alt="Sticker 26"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:118px;--rotate:7deg;--delay:-0.8s"><img src="{{ '/assets/img/art/mouse-10.png' | relative_url }}" alt="Sticker 27"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:92px;--rotate:-10deg;--delay:-2.6s"><img src="{{ '/assets/img/art/ball-08.png' | relative_url }}" alt="Sticker 28"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:114px;--rotate:5deg;--delay:-1.4s"><img src="{{ '/assets/img/art/rat-11.png' | relative_url }}" alt="Sticker 29"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:128px;--rotate:-3deg;--delay:-3.5s"><img src="{{ '/assets/img/art/mouse-11.png' | relative_url }}" alt="Sticker 30"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:102px;--rotate:9deg;--delay:-2.2s"><img src="{{ '/assets/img/art/ball-09.png' | relative_url }}" alt="Sticker 31"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:110px;--rotate:-7deg;--delay:-0.9s"><img src="{{ '/assets/img/art/rat-12.png' | relative_url }}" alt="Sticker 32"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:120px;--rotate:4deg;--delay:-1.8s"><img src="{{ '/assets/img/art/mouse-12.png' | relative_url }}" alt="Sticker 33"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:96px;--rotate:-4deg;--delay:-3.8s"><img src="{{ '/assets/img/art/rat-13.png' | relative_url }}" alt="Sticker 34"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:116px;--rotate:11deg;--delay:-2.5s"><img src="{{ '/assets/img/art/mouse-13.png' | relative_url }}" alt="Sticker 35"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:104px;--rotate:-9deg;--delay:-1.2s"><img src="{{ '/assets/img/art/rat-14.png' | relative_url }}" alt="Sticker 36"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:126px;--rotate:6deg;--delay:-3s"><img src="{{ '/assets/img/art/mouse-14.png' | relative_url }}" alt="Sticker 37"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:100px;--rotate:-2deg;--delay:-2s"><img src="{{ '/assets/img/art/rat-15.png' | relative_url }}" alt="Sticker 38"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:118px;--rotate:8deg;--delay:-0.4s"><img src="{{ '/assets/img/art/mouse-15.png' | relative_url }}" alt="Sticker 39"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:108px;--rotate:-5deg;--delay:-2.7s"><img src="{{ '/assets/img/art/rat-16.png' | relative_url }}" alt="Sticker 40"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:124px;--rotate:3deg;--delay:-1.6s"><img src="{{ '/assets/img/art/mouse-16.png' | relative_url }}" alt="Sticker 41"></button>
  <button class="art-piece" type="button" data-kind="sticker" style="--size:112px;--rotate:-8deg;--delay:-3.2s"><img src="{{ '/assets/img/art/mouse-17.png' | relative_url }}" alt="Sticker 42"></button>
</div>

<div class="art-viewer" id="art-viewer" aria-hidden="true">
  <div class="art-viewer__inner">
    <button class="art-viewer__close" type="button" aria-label="Close artwork viewer">&times;</button>
    <img class="art-viewer__image" src="" alt="">
  </div>
</div>

<script>
  (() => {
    const filters = document.querySelectorAll(".art-filter");
    const pieces = document.querySelectorAll(".art-piece");
    const viewer = document.getElementById("art-viewer");
    const viewerImage = viewer.querySelector(".art-viewer__image");
    const closeButton = viewer.querySelector(".art-viewer__close");

    filters.forEach((filter) => {
      filter.addEventListener("click", () => {
        const kind = filter.dataset.filter;
        filters.forEach((item) => item.classList.toggle("is-active", item === filter));
        pieces.forEach((piece) => {
          const visible = kind === "all" || piece.dataset.kind === kind;
          piece.classList.toggle("is-hidden", !visible);
        });
      });
    });

    pieces.forEach((piece) => {
      piece.addEventListener("click", () => {
        const image = piece.querySelector("img");
        viewerImage.src = image.currentSrc || image.src;
        viewerImage.alt = image.alt;
        viewer.classList.add("is-open");
        viewer.setAttribute("aria-hidden", "false");
        closeButton.focus();
      });
    });

    const closeViewer = () => {
      viewer.classList.remove("is-open");
      viewer.setAttribute("aria-hidden", "true");
      viewerImage.src = "";
    };

    closeButton.addEventListener("click", closeViewer);
    viewer.addEventListener("click", (event) => {
      if (event.target === viewer) closeViewer();
    });
    document.addEventListener("keydown", (event) => {
      if (event.key === "Escape" && viewer.classList.contains("is-open")) closeViewer();
    });
  })();
</script>
