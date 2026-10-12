<script lang="ts">
  type Project = { title: string; description: string; image: string; tags: string[]; links: { label: string; href: string }[] };

  const bioinformatics: Project[] = [
    {
      title: 'CZI Gene Expression Mapping',
      description: 'Exploring human single-cell gene expression across datasets, cell types, and tissues using aggregated CELLxGENE data.',
      image: '',
      tags: ['Python', 'Django', 'PostgreSQL', 'Plotly'],
      links: [
        {
          label: 'Visit Website',
          href: 'https://czi.radatech.org'
        },
        {
          label: 'GitHub',
          href: 'https://github.com/Radatech-LLC/czi_gene_expression_source_data'
        }
      ]
    },
    { title: 'Vaccination Coverage & Cases', description: 'Capstone project combining Project Tycho and CDC NIS-Child data for analysis and interactive presentation.', image: '/img/capstone-project.PNG', tags: ['Data analysis', 'Streamlit'], links: [{ label: 'Live application', href: 'https://biot670i-group1.streamlit.app/' }] },
    { title: 'TRPV1 Agonist Discovery', description: 'Training a ChemProp model using ChEMBL data to predict activity of novel compounds.', image: '/img/trpv1-ml.PNG', tags: ['Machine learning', 'ChemProp'], links: [{ label: 'GitHub', href: 'https://github.com/FusRaDa/trpv1-drug-disovery-chemprop' }] },
    { title: 'nf-core / RNA-seq', description: 'Running an nf-core RNA-seq workflow using Nextflow and visualizing expression counts.', image: '/img/nf-core-rnaseq.PNG', tags: ['Nextflow', 'RNA-seq'], links: [{ label: 'GitHub', href: 'https://github.com/FusRaDa/RNAseq-nf-core' }] },
    { title: 'ToxPi Model Weights', description: 'Reproducing results from Fleming et al. with Nextflow and R.', image: '/img/Figure_10.png', tags: ['R', 'Nextflow'], links: [{ label: 'GitHub', href: 'https://github.com/FusRaDa/PMC11175362_reproduce_nf?tab=readme-ov-file' }] },
    { title: 'Mothur & Metagenomics', description: 'Integrating the mothur MiSeq SOP tutorial into a Nextflow workflow.', image: '/img/mothur-nf.png', tags: ['Metagenomics', 'Nextflow'], links: [{ label: 'GitHub', href: 'https://github.com/FusRaDa/miseq_sop_nextflow' }] },
    { title: 'PCRprep', description: 'A project designed for sample accessioning and PCR assays.', image: '/img/pcr-prep-logo.png', tags: ['Laboratory workflows'], links: [{ label: 'GitHub', href: 'https://github.com/FusRaDa/pcr-project-2023-global' }, { label: 'Video', href: 'https://youtu.be/IJtDBgoFGRQ?si=V6MWACA7q3hADEBm' }] }
  ];

  const webProjects: Project[] = [
    { title: 'Sunlight Right', description: 'An application estimating potential vitamin D exposure from sunlight.', image: '/img/sunlightright.png', tags: ['Web application'], links: [{ label: 'Visit website', href: 'https://sunlightright.org/' }] },
    { title: 'Hope Channel International', description: 'Web specialist contract work supporting Hope Channel International since 2023.', image: '/img/HC Logo.png', tags: ['Web development', 'Contract work'], links: [{ label: 'Visit website', href: 'https://hopechannelinternational.org/' }] },
    { title: 'Caring Angels LLC', description: 'Website development for a caregiving agency serving the DMV area.', image: '/img/logo-transparent.png', tags: ['Client website'], links: [{ label: 'Visit website', href: 'https://caring-angels-llc.com/' }] }
  ];

  const otherProjects: Project[] = [
    { title: 'Autoflusher Bot', description: 'A 3D-printed Arduino-powered robot built to flush a toilet.', image: '/img/robot.jpg', tags: ['Arduino', '3D printing'], links: [{ label: 'Watch video', href: 'https://youtu.be/WqopIXGkR5I?si=rA0KsFy9vCWZ8E_3' }] }
  ];

  const skills = ['Python', 'pandas', 'PostgreSQL', 'Django', 'Streamlit', 'Nextflow', 'R', 'Svelte', 'JavaScript', 'Plotly', 'Bioinformatics', 'Data visualization'];
</script>

<svelte:head>
  <title>Christopher M. Rada | Bioinformatics & Software Development</title>
  <meta name="description" content="Portfolio of Christopher M. Rada: bioinformatics, scientific data analysis, and web development projects." />
</svelte:head>

<div class="portfolio">
  <header class="topbar shell">
    <a class="brand" href="#top">CMR<span>.</span></a>
    <nav aria-label="Main navigation">
      <a href="#projects">Projects</a>
      <a href="#web">Web work</a>
      <a href="#skills">Skills</a>
      <a class="nav-contact" href="mailto:matthewr7.christopher@gmail.com">Contact ↗</a>
    </nav>
  </header>

  <main id="top">
    <section class="hero shell">
      <div class="hero-copy">
        <div class="eyebrow"><span class="status-dot"></span> BIOINFORMATICS · SOFTWARE DEVELOPMENT</div>
        <h1>Hi, I'm <span>Christopher M. Rada.</span></h1>
        <p class="hero-lead">I turn complex biological data into useful tools, insightful visualizations, and accessible web experiences.</p>
        <p class="hero-sub">Graduate biotechnology student with a focus on bioinformatics, scientific computing, and full-stack development.</p>
        <div class="hero-actions">
          <a class="primary-action" href="#projects">Explore my work <span>↗</span></a>
          <a class="secondary-action" href="https://www.linkedin.com/in/christopher-rada-a657a51b6/" target="_blank" rel="noopener noreferrer">LinkedIn ↗</a>
          <a class="secondary-action" href="https://github.com/FusRaDa" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
        </div>
      </div>
      <div class="portrait-frame"><img src="/img/matthew-rada-img.jpg" alt="Portrait of Christopher M. Rada" /></div>
    </section>

    <section id="projects" class="section shell">
      <div class="section-heading"><div><p class="kicker">01 / RESEARCH & COMPUTING</p><h2>Bioinformatics projects<span>.</span></h2></div><p>Scientific workflows, computational biology, and data-driven applications.</p></div>
      <div class="project-grid">
        {#each bioinformatics as project, i}
          <article class:featured={i === 0} class="project-card">
            <div class="project-media" class:no-image={!project.image}>
              {#if project.image}<img src={project.image} alt="{project.title} project preview" loading="lazy" />{:else}<div class="placeholder-art"><span>GENE / EXPRESSION</span><strong>CZI<span>·</span>DATA</strong><small>Single-cell expression explorer</small></div>{/if}
            </div>
            <div class="project-content"><div class="tags">{#each project.tags as tag}<span>{tag}</span>{/each}</div><h3>{project.title}</h3><p>{project.description}</p><div class="project-links">{#each project.links as link}<a href={link.href} target="_blank" rel="noopener noreferrer">{link.label} ↗</a>{/each}</div></div>
          </article>
        {/each}
      </div>
    </section>

    <section id="web" class="section shell">
      <div class="section-heading"><div><p class="kicker">02 / DEVELOPMENT & CLIENT WORK</p><h2>Web development<span>.</span></h2></div><p>Web applications and professional work through Radatech LLC.</p></div>
      <div class="project-grid">{#each webProjects as project}<article class="project-card"><div class="project-media"><img src={project.image} alt="{project.title} preview" loading="lazy" /></div><div class="project-content"><div class="tags">{#each project.tags as tag}<span>{tag}</span>{/each}</div><h3>{project.title}</h3><p>{project.description}</p><div class="project-links">{#each project.links as link}<a href={link.href} target="_blank" rel="noopener noreferrer">{link.label} ↗</a>{/each}</div></div></article>{/each}</div>
    </section>

    <section id="skills" class="section shell"><div class="section-heading"><div><p class="kicker">03 / TOOLKIT</p><h2>Technical skills<span>.</span></h2></div><p>Tools and technologies across data science, biology, and web development.</p></div><div class="skill-list">{#each skills as skill}<span>{skill}</span>{/each}</div></section>

    <section class="section shell other-section"><div class="section-heading"><div><p class="kicker">04 / BEYOND THE SCREEN</p><h2>Other projects<span>.</span></h2></div></div><div class="project-grid">{#each otherProjects as project}<article class="project-card"><div class="project-media"><img src={project.image} alt="{project.title} preview" loading="lazy" /></div><div class="project-content"><div class="tags">{#each project.tags as tag}<span>{tag}</span>{/each}</div><h3>{project.title}</h3><p>{project.description}</p><div class="project-links">{#each project.links as link}<a href={link.href} target="_blank" rel="noopener noreferrer">{link.label} ↗</a>{/each}</div></div></article>{/each}</div></section>

    <section class="contact-section shell"><p class="kicker">LET'S CONNECT</p><h2>Have something in mind?</h2><p>I'm interested in opportunities at the intersection of bioinformatics, data, and software development.</p><a class="primary-action" href="mailto:matthewr7.christopher@gmail.com">Get in touch ↗</a></section>
  </main>
  <footer class="shell"><span>© {new Date().getFullYear()} Christopher M. Rada</span><a href="#top">Back to top ↑</a></footer>
</div>

<style>
  :global(html){scroll-behavior:smooth} :global(body){margin:0} :global(*){box-sizing:border-box}
  .portfolio{--bg:#080e1b;--surface:#111b2c;--line:#26344a;--muted:#9aa9bf;--accent:#69d9f2;background:linear-gradient(180deg,rgba(5,12,24,.79),rgba(5,12,24,.91) 48%,rgba(5,12,24,.96)),url("/img/background.jpg") center top / cover fixed no-repeat;background-color:var(--bg);color:#edf4ff;font-family:Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;min-height:100vh;line-height:1.6}
  .portfolio a{text-decoration:none}.shell{width:min(1160px,calc(100% - 44px));margin-inline:auto}
  .topbar{height:86px;display:flex;align-items:center;justify-content:space-between;border-bottom:1px solid var(--line)}.brand{font-size:1.55rem;font-weight:850;letter-spacing:-.06em;color:#fff}.brand span,h2 span{color:var(--accent)}nav{display:flex;align-items:center;gap:30px}nav a{font-size:.88rem;color:#aebcd1;font-weight:600}nav a:hover,.secondary-action:hover,.project-links a:hover{color:var(--accent)}.nav-contact{border:1px solid #3c5871;padding:9px 16px;border-radius:8px}
  .hero{display:grid;grid-template-columns:minmax(0,1.4fr) minmax(230px,.65fr);align-items:center;gap:70px;padding-block:110px 120px}.eyebrow,.kicker{font-size:.74rem;font-weight:800;letter-spacing:.17em;color:var(--accent)}.eyebrow{display:flex;align-items:center;gap:10px}.status-dot{height:8px;width:8px;border-radius:50%;background:#6de7b1;box-shadow:0 0 15px #6de7b177}.hero h1{font-size:clamp(3rem,6vw,5.7rem);line-height:1.08;letter-spacing:-.065em;font-weight:850;margin:24px 0}.hero h1 span{color:var(--accent)}.hero-lead{font-size:clamp(1.15rem,2vw,1.45rem);color:#d4e2f2;max-width:690px;line-height:1.5}.hero-sub{color:var(--muted);max-width:620px;margin-top:16px}.hero-actions{display:flex;flex-wrap:wrap;align-items:center;gap:15px;margin-top:32px}.primary-action{display:inline-flex;gap:24px;align-items:center;background:var(--accent);color:#071321!important;border-radius:9px;padding:13px 20px;font-weight:800}.primary-action:hover{background:#a1eafa}.secondary-action{color:#d5e1f1;padding:12px 4px;font-weight:700}.portrait-frame{aspect-ratio:4/4.6;border-radius:20px;overflow:hidden;border:1px solid #3b5167;box-shadow:25px 25px 0 #13253a;background:#1d3047}.portrait-frame img{width:100%;height:100%;object-fit:cover}
  .section{padding-block:60px 45px;scroll-margin-top:30px}.section-heading{display:flex;justify-content:space-between;align-items:end;gap:30px;margin-bottom:32px}.section-heading h2{font-size:clamp(2rem,4vw,3rem);letter-spacing:-.05em;line-height:1.2;margin:10px 0 0;font-weight:800}.section-heading>p{color:var(--muted);max-width:350px;margin:0}.project-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:20px}.project-card{min-width:0;background:var(--surface);border:1px solid var(--line);border-radius:14px;overflow:hidden;display:flex;flex-direction:column;transition:transform .2s,border-color .2s}.project-card:hover{transform:translateY(-4px);border-color:#5283a1}.project-media{height:195px;background:#1a2940;overflow:hidden}.project-media img{width:100%;height:100%;object-fit:cover;display:block}.project-content{padding:23px;display:flex;flex-direction:column;flex:1}.tags{display:flex;flex-wrap:wrap;gap:7px}.tags span,.skill-list span{border:1px solid #2b4a60;background:#122c3d;color:#9cdef0;border-radius:6px;padding:4px 9px;font-size:.72rem;font-weight:700}.project-content h3{font-size:1.18rem;line-height:1.35;letter-spacing:-.02em;margin:16px 0 8px;font-weight:750}.project-content p{color:var(--muted);font-size:.92rem;line-height:1.65;margin:0 0 22px}.project-links{margin-top:auto;display:flex;flex-wrap:wrap;gap:18px}.project-links a{color:var(--accent);font-size:.86rem;font-weight:750}.featured{grid-column:span 2;display:grid;grid-template-columns:1fr 1fr}.featured .project-media{height:100%;min-height:280px}.featured .project-content{justify-content:center;padding:30px}.featured h3{font-size:1.65rem}.placeholder-art{height:100%;min-height:280px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:14px;background:radial-gradient(circle at 30% 30%,#245d79 0%,#10283f 48%,#0b1628 100%);color:#c5e8f3}.placeholder-art>span{font-size:.68rem;letter-spacing:.2em;font-weight:800}.placeholder-art strong{font-size:clamp(2rem,3vw,3.5rem);letter-spacing:-.08em}.placeholder-art strong span{color:var(--accent)}.placeholder-art small{color:#a3c6d8}
  .skill-list{display:flex;flex-wrap:wrap;gap:12px}.skill-list span{padding:11px 16px;font-size:.9rem;background:#111f30}.other-section{padding-bottom:100px}.contact-section{border-top:1px solid var(--line);padding-block:75px 85px;text-align:center}.contact-section h2{font-size:clamp(2rem,4vw,3.5rem);letter-spacing:-.05em;margin:10px 0}.contact-section>p:not(.kicker){color:var(--muted);max-width:540px;margin:0 auto 27px}.contact-section .primary-action{margin:auto}footer{display:flex;justify-content:space-between;gap:20px;padding-block:25px;border-top:1px solid var(--line);font-size:.83rem;color:var(--muted)}footer a{color:var(--accent)}
  @media(max-width:900px){.hero{gap:35px;padding-block:75px}.project-grid{grid-template-columns:repeat(2,minmax(0,1fr))}.featured{grid-column:span 2}}
  @media(max-width:640px){.shell{width:min(100% - 32px,1160px)}.topbar{height:auto;padding-block:18px;align-items:flex-start;gap:16px}nav{gap:12px;flex-wrap:wrap;justify-content:flex-end}nav a{font-size:.76rem}.nav-contact{padding:5px 9px}.hero{grid-template-columns:1fr;padding-block:65px 75px}.portrait-frame{width:min(75%,300px);margin:auto;aspect-ratio:1}.hero h1{font-size:clamp(2.7rem,11vw,4.5rem)}.section-heading{display:block}.section-heading>p{margin-top:14px}.project-grid{grid-template-columns:1fr}.featured{grid-column:auto;display:flex}.featured .project-media{height:210px;min-height:0}.project-media{height:210px}.featured .project-content{padding:23px}.featured h3{font-size:1.25rem}.section{padding-block:45px 25px}.other-section{padding-bottom:65px}footer{flex-wrap:wrap}}
  @media(prefers-reduced-motion:reduce){:global(html){scroll-behavior:auto}.project-card{transition:none}}
</style>
