---
layout: about
title: about
permalink: /
subtitle: computer engineering, robotics, perception, and mechanical systems.

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <div class="profile-meta">
      <p class="profile-meta__school">HKUST Computer Engineering</p>
      <p><a href="mailto:kluoaf@connect.ust.hk">kluoaf@connect.ust.hk</a></p>
    </div>

selected_papers: false # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

announcements:
  enabled: false # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 3 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

<style>
  .post {
    position: relative;
    isolation: isolate;
  }

  .post::before {
    content: "";
    position: absolute;
    z-index: -2;
    top: -5rem;
    left: 50%;
    width: 100vw;
    height: min(74vh, 680px);
    min-height: 560px;
    transform: translateX(-50%);
    background:
      linear-gradient(90deg, rgba(3, 8, 14, 0.86) 0%, rgba(3, 8, 14, 0.52) 42%, rgba(3, 8, 14, 0.28) 100%),
      linear-gradient(180deg, rgba(3, 8, 14, 0.1) 0%, rgba(3, 8, 14, 0.44) 62%, var(--global-bg-color) 100%),
      url("{{ '/assets/img/home-mountain-bg-soft.jpg' | relative_url }}");
    background-size: cover;
    background-position: center 52%;
  }

  .post::after {
    content: "";
    position: absolute;
    z-index: -1;
    top: -5rem;
    left: 50%;
    width: 100vw;
    height: min(74vh, 680px);
    min-height: 560px;
    transform: translateX(-50%);
    background:
      radial-gradient(circle at 64% 46%, rgba(255, 255, 255, 0.14), transparent 28%),
      linear-gradient(180deg, transparent 55%, var(--global-bg-color) 96%);
    pointer-events: none;
  }

  .post-header {
    min-height: clamp(92px, 13vh, 136px);
    padding-top: clamp(4rem, 9vw, 6.4rem);
    margin-bottom: clamp(0.15rem, 0.8vw, 0.55rem);
  }

  .post-header .post-title,
  .post-header .desc {
    color: #fff;
    text-shadow: 0 2px 18px rgba(0, 0, 0, 0.42);
  }

  .post-header .desc {
    max-width: 680px;
    opacity: 0.86;
    font-size: 1.02rem;
    font-weight: 300;
    line-height: 1.45;
  }

  .profile.float-right {
    position: relative;
    z-index: 2;
  }

  .profile img {
    border: 1px solid rgba(255, 255, 255, 0.24);
    box-shadow: 0 18px 44px rgba(0, 0, 0, 0.28);
  }

  .profile .more-info {
    margin-top: 0.85rem;
    padding: 0.58rem 0.72rem;
    border-radius: 6px;
    background: rgba(5, 10, 17, 0.42);
    backdrop-filter: blur(8px);
  }

  .profile-meta {
    font-family: Roboto, "Helvetica Neue", Arial, sans-serif;
    font-size: 0.84rem;
    line-height: 1.42;
    color: rgba(255, 255, 255, 0.7);
  }

  .profile-meta p {
    margin: 0.08rem 0;
  }

  .profile-meta__school {
    color: rgba(255, 255, 255, 0.92);
    font-weight: 500;
  }

  .profile-meta a {
    color: rgba(255, 255, 255, 0.78);
    text-decoration: none;
  }

  .profile-meta a:hover,
  .profile-meta a:focus-visible {
    color: var(--global-theme-color);
    text-decoration: underline;
  }

  .clearfix > p:nth-of-type(-n + 2) {
    max-width: 680px;
    color: rgba(255, 255, 255, 0.9);
    font-size: 1.02rem;
    font-weight: 300;
    line-height: 1.66;
    text-shadow: 0 2px 16px rgba(0, 0, 0, 0.42);
  }

  .clearfix > h2:first-of-type {
    clear: both;
    padding-top: clamp(11rem, 26vh, 14rem);
  }

  @media (min-width: 768px) {
    article {
      display: grid;
      grid-template-columns: minmax(0, 1fr) minmax(230px, 270px);
      column-gap: clamp(2rem, 4.8vw, 3.8rem);
      align-items: start;
    }

    .profile.float-right {
      float: none !important;
      grid-column: 2;
      grid-row: 1;
      width: 100%;
      margin: 0;
      align-self: start;
    }

    .clearfix {
      grid-column: 1;
      grid-row: 1;
    }

    .clearfix > p:nth-of-type(-n + 2) {
      max-width: none;
      margin-right: 0;
    }

    .clearfix > p:first-of-type {
      margin-top: 0;
    }

    .clearfix > h2:first-of-type,
    .clearfix > h2:first-of-type ~ * {
      margin-right: calc(-270px - clamp(2rem, 4.8vw, 3.8rem));
    }
  }

  @media (max-width: 767px) {
    .post::before,
    .post::after {
      height: 760px;
      min-height: 760px;
      background-position: 55% center;
    }

    .post-header {
      min-height: 118px;
      padding-top: 4.5rem;
      margin-bottom: 0.75rem;
    }

    .profile.float-right {
      float: none !important;
      width: min(76vw, 320px);
      margin: 0 auto 1.3rem;
    }

    .clearfix > h2:first-of-type {
      padding-top: 3rem;
    }
  }
</style>

Hi, I am Koukou Luo, a Computer Engineering undergraduate at the Hong Kong University of Science and Technology. I work across robotics, perception, mechanical systems, embedded systems, and advanced manufacturing.

I am currently an undergraduate researcher on humanoids, supervised by Prof. Ping Tan. My previous research and project work includes continuous carbon fiber additive manufacturing and aerial robot mechanical systems for RoboMaster.

## Education

- **Hong Kong University of Science and Technology**, BEng in Computer Engineering, expected Jun 2027
- **ETH Zurich**, exchange student, Sep 2025 - Feb 2026

## Selected Recognition

- HKSAR Government Scholarship Fund - Talent Development Scholarship
- University's Scholarship Scheme for Continuing Undergraduate Students
- Dean's List honors across multiple semesters
- First Prize, RoboMaster 2024 University Championship Regional Competition, Hong Kong, Macau, Taiwan, and Overseas Division
- Second Prize, RoboMaster 2024 University Championship Final Tournament

## Publication

Xu, Z., He, S., Luo, K., Chen, S., & Duan, M. (2025). "Additive Manufacturing With Continuous Fiber: A Comparison Between Prepreg and In-Situ Impregnated Fiber on Printing Accuracy, Bonding, and Mechanical Performance." Manufacturing Science and Engineering Conference (MSEC 2025), Greenville, USA.

## Skills

- **Programming and systems:** C++, Python, System Verilog, VHDL, Linux, embedded systems with STM32
- **Robotics and simulation:** Isaac Lab, perception, sensing and control collaboration
- **Mechanical design:** SolidWorks, 3D mechanical design, composite material structures
- **Languages:** Mandarin native, English advanced, IELTS 7.5
