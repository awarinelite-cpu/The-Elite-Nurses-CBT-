<script lang="ts">
  import { BookOpen, ClipboardCheck, Bookmark, TrendingUp, ArrowUpRight, ArrowRight, Bell, Search, ChevronRight, Menu, GraduationCap, Clock3, Flame } from 'lucide-svelte';
  import { subjects, recentActivity } from '$lib/data';
  let active = 'Dashboard';
  const nav = [
    { label: 'Dashboard', icon: TrendingUp, href: '/dashboard' },
    { label: 'Reading Mode', icon: BookOpen, href: '/reading' },
    { label: 'Exam Mode', icon: ClipboardCheck, href: '/exams' },
    { label: 'My Bookmarks', icon: Bookmark, href: '/reading' }
  ];
</script>

<svelte:head><title>Student Dashboard · THE ELITES NURSES</title></svelte:head>
<div class="app-shell">
  <aside class="sidebar">
    <a class="brand sidebar-brand" href="/"><span class="brand-mark">E<span>+</span></span><span class="brand-name">THE ELITES <b>NURSES</b><small>LEARN. PRACTISE. EXCEL.</small></span></a>
    <div class="sidebar-label">STUDY SPACE</div>
    <nav class="side-nav">{#each nav as item}<a class:active={active === item.label} href={item.href} onclick={() => active = item.label}><item.icon size={18}/>{item.label}{#if item.label === 'My Bookmarks'}<span class="side-count">12</span>{/if}</a>{/each}</nav>
    <div class="sidebar-label second-label">YOUR ACCOUNT</div>
    <nav class="side-nav"><a href="/dashboard"><GraduationCap size={18}/>My performance</a><a href="/dashboard"><Bell size={18}/>Notifications</a><a href="/dashboard">⚙️ Settings</a></nav>
    <div class="sidebar-bottom"><div class="upgrade-card"><span class="upgrade-spark">✦</span><b>Go further with Pro</b><p>Unlock the complete question library and full mock exams.</p><a href="#upgrade">Explore Pro <ArrowRight size={14}/></a></div><div class="user-mini"><div class="user-avatar">EN</div><div><b>Elites Student</b><small>Free account</small></div><span>•••</span></div></div>
  </aside>
  <main class="dashboard-main">
    <header class="dash-topbar"><div><span class="mobile-brand">THE ELITES NURSES</span><div class="breadcrumb">Study space <ChevronRight size={14}/> <b>Dashboard</b></div></div><div class="topbar-actions"><label class="search-box"><Search size={16}/><input placeholder="Search subjects, topics..."/></label><button class="icon-button" aria-label="Notifications"><Bell size={18}/><i></i></button><div class="user-avatar top-avatar">EN</div></div></header>
    <div class="dash-content">
      <section class="welcome-row"><div><div class="eyebrow">MONDAY, 24 NOVEMBER 2026</div><h1>Welcome back, <em>future nurse.</em></h1><p>Every focused session brings you closer to your goal. Let's make today count.</p></div><div class="streak-pill"><Flame size={17}/> <b>4 day streak</b></div></section>
      <section class="stats-grid">
        <article class="stat-card"><div class="stat-top"><span>Questions studied</span><span class="stat-icon sage"><BookOpen size={18}/></span></div><strong>248</strong><small><span class="positive">+18</span> this week</small></article>
        <article class="stat-card"><div class="stat-top"><span>Average score</span><span class="stat-icon gold"><TrendingUp size={18}/></span></div><strong>82<small class="unit">%</small></strong><small><span class="positive">+6%</span> from last week</small></article>
        <article class="stat-card"><div class="stat-top"><span>Exams completed</span><span class="stat-icon blue"><ClipboardCheck size={18}/></span></div><strong>12</strong><small>Keep the momentum going</small></article>
        <article class="stat-card"><div class="stat-top"><span>Saved questions</span><span class="stat-icon rose"><Bookmark size={18}/></span></div><strong>12</strong><small>Ready for revision</small></article>
      </section>
      <section class="mode-launch">
        <a href="/reading" class="launch-card launch-reading"><div class="launch-icon"><BookOpen size={23}/></div><div class="launch-copy"><span>LEARN AT YOUR OWN PACE</span><h2>Reading Mode</h2><p>Explore subjects, understand answers and build your knowledge topic by topic.</p><b>Continue reading <ArrowRight size={17}/></b></div><div class="launch-decoration">01</div></a>
        <a href="/exams" class="launch-card launch-exam"><div class="launch-icon"><ClipboardCheck size={23}/></div><div class="launch-copy"><span>PUT YOUR KNOWLEDGE TO TEST</span><h2>Exam Mode</h2><p>Take timed tests, practise past questions and prepare for exam day.</p><b>Start an examination <ArrowRight size={17}/></b></div><div class="launch-decoration">02</div></a>
      </section>
      <section class="lower-grid">
        <div class="panel subjects-panel"><div class="panel-heading"><div><h3>Continue learning</h3><p>Pick up where you left off.</p></div><a href="/reading">All subjects <ArrowUpRight size={16}/></a></div>
          <div class="subject-list">{#each subjects.slice(0,4) as subject}<a href="/reading" class="subject-row"><div class="subject-monogram tone-{subject.tone}">{subject.short}</div><div class="subject-info"><b>{subject.name}</b><small>{subject.questions} questions available</small><div class="subject-progress"><span style={`width:${subject.progress}%`}></span></div></div><div class="subject-percent">{subject.progress}%</div><ChevronRight size={17} class="subject-chevron"/></a>{/each}</div>
        </div>
        <div class="panel activity-panel"><div class="panel-heading"><div><h3>Recent activity</h3><p>Your latest study sessions.</p></div><Clock3 size={18}/></div>
          <div class="activity-list">{#each recentActivity as activity}<div class="activity-item"><div class="activity-marker"></div><div class="activity-info"><b>{activity.title}</b><small>{activity.detail}</small><small class="activity-date">{activity.date}</small></div><strong>{activity.score}</strong></div>{/each}</div>
          <a href="/exams" class="activity-footer">View all results <ArrowRight size={15}/></a>
        </div>
      </section>
      <section class="daily-tip"><div class="tip-icon">✦</div><div><small>A LITTLE REMINDER</small><b>Consistency beats cramming.</b><p>Try a short revision session today, even if you only have 15 minutes.</p></div><span class="tip-decoration">✳</span></section>
    </div>
  </main>
</div>
