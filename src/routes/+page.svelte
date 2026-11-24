<script lang="ts">
  import { ArrowRight, BookOpen, ClipboardCheck, GraduationCap, ShieldCheck, Menu, X, CheckCircle2, Sparkles } from 'lucide-svelte';
  let menuOpen = false;
</script>

<svelte:head>
  <title>THE ELITES NURSES — Learn. Practise. Excel.</title>
</svelte:head>

<header class="site-header">
  <a class="brand" href="/" aria-label="The Elites Nurses home">
    <span class="brand-mark">E<span>+</span></span>
    <span class="brand-name">THE ELITES <b>NURSES</b><small>LEARN. PRACTISE. EXCEL.</small></span>
  </a>
  <button class="mobile-menu" aria-label="Toggle menu" onclick={() => menuOpen = !menuOpen}>
    {#if menuOpen}<X size={22}/>{:else}<Menu size={22}/>{/if}
  </button>
  <nav class:open={menuOpen}>
    <a href="#features" onclick={() => menuOpen = false}>Features</a>
    <a href="#subjects" onclick={() => menuOpen = false}>Subjects</a>
    <a href="#how-it-works" onclick={() => menuOpen = false}>How it works</a>
    <a href="#pricing" onclick={() => menuOpen = false}>Pricing</a>
    <a class="nav-login" href="/login">Log in</a>
    <a class="button button-small" href="/dashboard">Get started <ArrowRight size={16}/></a>
  </nav>
</header>

<main>
  <section class="hero">
    <div class="hero-copy">
      <div class="eyebrow"><span class="eyebrow-dot"></span> YOUR NURSING EXAM COMPANION</div>
      <h1>Your journey to nursing exam success <em>starts here.</em></h1>
      <p class="hero-intro">Build confidence with focused revision, carefully organised nursing questions and realistic CBT practice — all in one place.</p>
      <div class="hero-actions">
        <a class="button" href="/dashboard">Start learning <ArrowRight size={18}/></a>
        <a class="button button-quiet" href="#features">Explore the platform</a>
      </div>
      <div class="trust-row">
        <div class="avatar-stack"><span>EN</span><span>RN</span><span>+</span></div>
        <p><strong>Made for nursing students</strong><br/>A clearer way to prepare, practise and improve.</p>
      </div>
    </div>
    <div class="hero-visual">
      <div class="visual-orbit orbit-one"></div><div class="visual-orbit orbit-two"></div>
      <div class="hero-card">
        <div class="hero-card-top"><span class="live-dot"></span> YOUR STUDY SPACE <span class="card-menu">•••</span></div>
        <div class="hero-card-title">Good morning, future nurse.</div>
        <p class="muted">A little progress every day adds up.</p>
        <div class="progress-block">
          <div class="progress-label"><span>Weekly study goal</span><b>4 of 5 days</b></div>
          <div class="progress-track"><span style="width:80%"></span></div>
        </div>
        <div class="mini-stats">
          <div><span class="mini-icon"><BookOpen size={17}/></span><b>248</b><small>Questions studied</small></div>
          <div><span class="mini-icon gold-icon"><ClipboardCheck size={17}/></span><b>82%</b><small>Average score</small></div>
        </div>
        <div class="next-up"><div class="next-icon"><GraduationCap size={20}/></div><div><small>UP NEXT</small><b>Fundamentals of Nursing</b></div><ArrowRight size={17}/></div>
      </div>
      <div class="floating-note"><span><CheckCircle2 size={17}/></span><div><b>Keep your momentum</b><small>You're making progress.</small></div></div>
      <div class="hero-stamp"><Sparkles size={18}/><span>LEARN WITH<br/>CONFIDENCE</span></div>
    </div>
  </section>

  <section class="feature-strip" id="features">
    <div><span class="strip-icon"><BookOpen size={20}/></span><div><b>Read & understand</b><small>Learn at your own pace</small></div></div>
    <div><span class="strip-icon"><ClipboardCheck size={20}/></span><div><b>Practise like the real exam</b><small>Build speed and confidence</small></div></div>
    <div><span class="strip-icon"><ShieldCheck size={20}/></span><div><b>Track your progress</b><small>Know where to improve</small></div></div>
  </section>

  <section class="section subjects-section" id="subjects">
    <div class="section-heading"><div><div class="eyebrow">YOUR LEARNING, ORGANISED</div><h2>Explore the subjects<br/><em>that shape great nurses.</em></h2></div><a href="/dashboard" class="text-link">View all subjects <ArrowRight size={16}/></a></div>
    <div class="subject-preview">
      <div class="subject-tile tile-green"><span>01</span><div class="tile-symbol">✚</div><h3>Fundamentals<br/>of Nursing</h3><small>Build a strong foundation</small></div>
      <div class="subject-tile tile-cream"><span>02</span><div class="tile-symbol">＋</div><h3>Medical-Surgical<br/>Nursing</h3><small>Understand clinical care</small></div>
      <div class="subject-tile tile-sage"><span>03</span><div class="tile-symbol">♡</div><h3>Maternal &<br/>Child Health</h3><small>Care across every stage</small></div>
      <div class="subject-tile tile-dark"><span>04</span><div class="tile-symbol">✳</div><h3>Community<br/>Health Nursing</h3><small>Think beyond the ward</small></div>
    </div>
  </section>

  <section class="section modes-section" id="how-it-works">
    <div class="center-heading"><div class="eyebrow">TWO WAYS TO GET READY</div><h2>Study your way.<br/><em>Show up prepared.</em></h2><p>Whether you're learning a topic for the first time or testing what you know, there's a mode for you.</p></div>
    <div class="mode-grid">
      <article class="mode-card reading-card"><div class="mode-kicker">01 / LEARN</div><div class="mode-illustration"><BookOpen size={40}/><span class="illustration-line"></span></div><h3>Reading Mode</h3><p>Work through questions by subject and topic. Reveal answers, understand explanations and save questions for revision.</p><a href="/reading" class="mode-link">Explore Reading Mode <ArrowRight size={17}/></a></article>
      <article class="mode-card exam-card"><div class="mode-kicker">02 / PRACTISE</div><div class="mode-illustration"><ClipboardCheck size={40}/><span class="illustration-line"></span></div><h3>Exam Mode</h3><p>Take timed mock exams, practise past questions and review your performance after every attempt.</p><a href="/exams" class="mode-link">Explore Exam Mode <ArrowRight size={17}/></a></article>
    </div>
  </section>

  <section class="cta-section" id="pricing"><div><div class="eyebrow light-eyebrow">YOUR NEXT CHAPTER STARTS NOW</div><h2>One question at a time.<br/><em>One step closer.</em></h2><p>Start building the knowledge and confidence to take your next nursing examination.</p></div><a href="/dashboard" class="button button-light">Enter your study space <ArrowRight size={18}/></a></section>
</main>

<footer class="site-footer"><a class="brand footer-brand" href="/"><span class="brand-mark">E<span>+</span></span><span class="brand-name">THE ELITES <b>NURSES</b><small>LEARN. PRACTISE. EXCEL.</small></span></a><p>Thoughtful preparation for the next generation of nurses.</p><small>© 2026 THE ELITES NURSES. All rights reserved.</small></footer>
