/* ============================================================
   PIEVETTI STUDIO — MAIN SCRIPT
   Loader · Custom Cursor · Canvas Hero · Reveal · Count-up
   Magnetic · Parallax · Nav scroll · Mobile menu
   ============================================================ */

(function () {
  'use strict';

  /* ──────────────────────────────────────────
     LOADER
  ────────────────────────────────────────── */
  const loader = document.getElementById('loader');
  const loaderFill = document.querySelector('.loader-fill');

  let progress = 0;
  const fillInterval = setInterval(() => {
    progress += Math.random() * 18 + 4;
    if (progress >= 100) {
      progress = 100;
      clearInterval(fillInterval);
      setTimeout(() => {
        loader.classList.add('hidden');
        initAnimations();
      }, 300);
    }
    loaderFill.style.width = Math.min(progress, 100) + '%';
  }, 80);

  /* ──────────────────────────────────────────
     CUSTOM CURSOR
  ────────────────────────────────────────── */
  const cursor = document.getElementById('cursor');
  const cursorTrail = document.getElementById('cursor-trail');

  if (cursor && cursorTrail) {
    let mouseX = 0, mouseY = 0;
    let trailX = 0, trailY = 0;

    document.addEventListener('mousemove', (e) => {
      mouseX = e.clientX;
      mouseY = e.clientY;
      cursor.style.left = mouseX + 'px';
      cursor.style.top = mouseY + 'px';
    });

    function updateTrail() {
      trailX += (mouseX - trailX) * 0.1;
      trailY += (mouseY - trailY) * 0.1;
      cursorTrail.style.left = trailX + 'px';
      cursorTrail.style.top = trailY + 'px';
      requestAnimationFrame(updateTrail);
    }
    updateTrail();

    // Hover states for interactive elements
    const hoverEls = document.querySelectorAll('a, button, [data-magnetic]');
    hoverEls.forEach(el => {
      el.addEventListener('mouseenter', () => document.body.classList.add('cursor-hover'));
      el.addEventListener('mouseleave', () => document.body.classList.remove('cursor-hover'));
    });
  }

  /* ──────────────────────────────────────────
     HERO CANVAS — Particle Field
     Fine dots forming a breathing, reactive grid
  ────────────────────────────────────────── */
  function initHeroCanvas() {
    const canvas = document.getElementById('heroCanvas');
    if (!canvas) return;
    const ctx = canvas.getContext('2d');

    let W, H, particles;
    let mouseX = -9999, mouseY = -9999;

    function resize() {
      W = canvas.width = canvas.offsetWidth;
      H = canvas.height = canvas.offsetHeight;
      initParticles();
    }

    class Particle {
      constructor() {
        this.reset(true);
      }
      reset(init = false) {
        this.x = Math.random() * W;
        this.y = init ? Math.random() * H : H + 10;
        this.baseX = this.x;
        this.baseY = this.y;
        this.size = Math.random() * 1.2 + 0.3;
        this.opacity = Math.random() * 0.4 + 0.05;
        this.speed = Math.random() * 0.3 + 0.1;
        this.vx = (Math.random() - 0.5) * 0.15;
        this.vy = -(Math.random() * 0.4 + 0.1);
      }
      update() {
        // Drift
        this.x += this.vx;
        this.y += this.vy;

        // Mouse repulsion
        const dx = this.x - mouseX;
        const dy = this.y - mouseY;
        const dist = Math.sqrt(dx * dx + dy * dy);
        if (dist < 120) {
          const force = (120 - dist) / 120;
          this.x += dx / dist * force * 1.5;
          this.y += dy / dist * force * 1.5;
        }

        if (this.y < -10) this.reset();
      }
      draw() {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
        ctx.fillStyle = `rgba(232, 201, 122, ${this.opacity})`;
        ctx.fill();
      }
    }

    function initParticles() {
      const count = Math.floor((W * H) / 9000);
      particles = Array.from({ length: count }, () => new Particle());
    }

    // Draw subtle connection lines
    function drawConnections() {
      for (let i = 0; i < particles.length; i++) {
        for (let j = i + 1; j < particles.length; j++) {
          const dx = particles[i].x - particles[j].x;
          const dy = particles[i].y - particles[j].y;
          const dist = Math.sqrt(dx * dx + dy * dy);
          if (dist < 80) {
            ctx.beginPath();
            ctx.strokeStyle = `rgba(232, 201, 122, ${0.06 * (1 - dist / 80)})`;
            ctx.lineWidth = 0.5;
            ctx.moveTo(particles[i].x, particles[i].y);
            ctx.lineTo(particles[j].x, particles[j].y);
            ctx.stroke();
          }
        }
      }
    }

    function animate() {
      ctx.clearRect(0, 0, W, H);

      // Subtle radial glow at bottom center
      const grd = ctx.createRadialGradient(W / 2, H, 0, W / 2, H, H * 0.6);
      grd.addColorStop(0, 'rgba(232,201,122,0.04)');
      grd.addColorStop(1, 'rgba(0,0,0,0)');
      ctx.fillStyle = grd;
      ctx.fillRect(0, 0, W, H);

      drawConnections();
      particles.forEach(p => { p.update(); p.draw(); });
      requestAnimationFrame(animate);
    }

    canvas.addEventListener('mousemove', (e) => {
      const rect = canvas.getBoundingClientRect();
      mouseX = e.clientX - rect.left;
      mouseY = e.clientY - rect.top;
    });
    canvas.addEventListener('mouseleave', () => { mouseX = -9999; mouseY = -9999; });

    window.addEventListener('resize', resize);
    resize();
    animate();
  }

  /* ──────────────────────────────────────────
     CTA CANVAS — Slow ambient glow
  ────────────────────────────────────────── */
  function initCtaCanvas() {
    const canvas = document.getElementById('ctaCanvas');
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    let W, H, t = 0;

    function resize() {
      W = canvas.width = canvas.offsetWidth;
      H = canvas.height = canvas.offsetHeight;
    }

    function animate() {
      ctx.clearRect(0, 0, W, H);
      t += 0.005;

      // Slow moving orbs
      const orbs = [
        { x: W * 0.3 + Math.sin(t) * W * 0.08, y: H * 0.5 + Math.cos(t * 0.7) * H * 0.2, r: W * 0.25, color: 'rgba(232,201,122,0.04)' },
        { x: W * 0.7 + Math.cos(t * 1.3) * W * 0.06, y: H * 0.5 + Math.sin(t) * H * 0.15, r: W * 0.2, color: 'rgba(232,201,122,0.025)' },
      ];

      orbs.forEach(orb => {
        const grd = ctx.createRadialGradient(orb.x, orb.y, 0, orb.x, orb.y, orb.r);
        grd.addColorStop(0, orb.color);
        grd.addColorStop(1, 'rgba(0,0,0,0)');
        ctx.fillStyle = grd;
        ctx.fillRect(0, 0, W, H);
      });

      requestAnimationFrame(animate);
    }

    window.addEventListener('resize', resize);
    resize();
    animate();
  }

  /* ──────────────────────────────────────────
     SCROLL REVEAL
  ────────────────────────────────────────── */
  function initReveal() {
    const els = document.querySelectorAll('[data-reveal]');
    if (!els.length) return;

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });

    els.forEach(el => observer.observe(el));
  }

  /* ──────────────────────────────────────────
     COUNT UP ANIMATION
  ────────────────────────────────────────── */
  function initCountUp() {
    const nums = document.querySelectorAll('[data-count]');
    if (!nums.length) return;

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const el = entry.target;
          const target = parseInt(el.dataset.count);
          let start = 0;
          const duration = 2000;
          const startTime = performance.now();

          function tick(now) {
            const elapsed = now - startTime;
            const progress = Math.min(elapsed / duration, 1);
            // Ease out expo
            const eased = 1 - Math.pow(1 - progress, 4);
            start = Math.floor(eased * target);
            el.textContent = start;
            if (progress < 1) requestAnimationFrame(tick);
          }
          requestAnimationFrame(tick);
          observer.unobserve(el);
        }
      });
    }, { threshold: 0.5 });

    nums.forEach(el => observer.observe(el));
  }

  /* ──────────────────────────────────────────
     MAGNETIC BUTTONS
  ────────────────────────────────────────── */
  function initMagnetic() {
    const els = document.querySelectorAll('[data-magnetic]');
    els.forEach(el => {
      el.addEventListener('mousemove', (e) => {
        const rect = el.getBoundingClientRect();
        const cx = rect.left + rect.width / 2;
        const cy = rect.top + rect.height / 2;
        const dx = e.clientX - cx;
        const dy = e.clientY - cy;
        el.style.transform = `translate(${dx * 0.22}px, ${dy * 0.22}px)`;
      });
      el.addEventListener('mouseleave', () => {
        el.style.transform = '';
      });
    });
  }

  /* ──────────────────────────────────────────
     NAV SCROLL
  ────────────────────────────────────────── */
  function initNav() {
    const nav = document.getElementById('nav');
    const hamburger = document.getElementById('hamburger');
    const navMobile = document.getElementById('navMobile');

    window.addEventListener('scroll', () => {
      if (window.scrollY > 40) {
        nav.classList.add('scrolled');
      } else {
        nav.classList.remove('scrolled');
      }
    }, { passive: true });

    if (hamburger && navMobile) {
      hamburger.addEventListener('click', () => {
        hamburger.classList.toggle('open');
        navMobile.classList.toggle('open');
      });

      // Close on link click
      navMobile.querySelectorAll('a').forEach(a => {
        a.addEventListener('click', () => {
          hamburger.classList.remove('open');
          navMobile.classList.remove('open');
        });
      });
    }
  }

  /* ──────────────────────────────────────────
     HERO LINE REVEAL
     Staggers each headline line on load
  ────────────────────────────────────────── */
  function initHeroReveal() {
    const lines = document.querySelectorAll('.hero-headline .line, .hero-headline em');
    lines.forEach((line, i) => {
      line.style.opacity = '0';
      line.style.transform = 'translateY(40px)';
      line.style.transition = `opacity 1s cubic-bezier(0.16, 1, 0.3, 1) ${0.15 + i * 0.12}s, transform 1s cubic-bezier(0.16, 1, 0.3, 1) ${0.15 + i * 0.12}s`;
    });

    const heroReveal = document.querySelectorAll('[data-reveal]');
    heroReveal.forEach((el, i) => {
      el.style.transitionDelay = `${0.1 + i * 0.1}s`;
    });

    // Trigger after loader
    setTimeout(() => {
      lines.forEach(line => {
        line.style.opacity = '1';
        line.style.transform = 'translateY(0)';
      });
      heroReveal.forEach(el => el.classList.add('visible'));
    }, 100);
  }

  /* ──────────────────────────────────────────
     SERVICE CARDS — tilt on hover
  ────────────────────────────────────────── */
  function initTilt() {
    const cards = document.querySelectorAll('.service-card, .result-card, .testimonial');
    cards.forEach(card => {
      card.addEventListener('mousemove', (e) => {
        const rect = card.getBoundingClientRect();
        const x = (e.clientX - rect.left) / rect.width - 0.5;
        const y = (e.clientY - rect.top) / rect.height - 0.5;
        card.style.transform = `perspective(800px) rotateY(${x * 3}deg) rotateX(${-y * 3}deg) translateZ(4px)`;
      });
      card.addEventListener('mouseleave', () => {
        card.style.transform = '';
      });
    });
  }

  /* ──────────────────────────────────────────
     SMOOTH SCROLL
  ────────────────────────────────────────── */
  function initSmoothScroll() {
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', (e) => {
        const target = document.querySelector(anchor.getAttribute('href'));
        if (target) {
          e.preventDefault();
          target.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      });
    });
  }

  /* ──────────────────────────────────────────
     FLOAT CTA — show after scroll
  ────────────────────────────────────────── */
  function initFloatCTA() {
    const floatCTA = document.getElementById('floatCTA');
    if (!floatCTA) return;
    floatCTA.style.opacity = '0';
    floatCTA.style.transform = 'scale(0.8)';
    floatCTA.style.transition = 'opacity 0.5s, transform 0.5s';

    window.addEventListener('scroll', () => {
      if (window.scrollY > 300) {
        floatCTA.style.opacity = '1';
        floatCTA.style.transform = 'scale(1)';
      } else {
        floatCTA.style.opacity = '0';
        floatCTA.style.transform = 'scale(0.8)';
      }
    }, { passive: true });
  }

  /* ──────────────────────────────────────────
     MARQUEE — pause on hover
  ────────────────────────────────────────── */
  function initMarquee() {
    const inner = document.querySelector('.marquee-inner');
    if (!inner) return;
    inner.addEventListener('mouseenter', () => inner.style.animationPlayState = 'paused');
    inner.addEventListener('mouseleave', () => inner.style.animationPlayState = 'running');
  }

  /* ──────────────────────────────────────────
     SCROLL VELOCITY effect on marquee speed
  ────────────────────────────────────────── */
  function initScrollVelocity() {
    let lastScroll = 0;
    let velocity = 0;
    const inner = document.querySelector('.marquee-inner');
    if (!inner) return;

    window.addEventListener('scroll', () => {
      const current = window.scrollY;
      velocity = Math.abs(current - lastScroll);
      lastScroll = current;

      const speed = Math.max(28 - velocity * 0.5, 8);
      inner.style.animationDuration = speed + 's';
    }, { passive: true });
  }

  /* ──────────────────────────────────────────
     INIT — called after loader finishes
  ────────────────────────────────────────── */
  function initAnimations() {
    initHeroReveal();
    initHeroCanvas();
    initCtaCanvas();
    initReveal();
    initCountUp();
    initMagnetic();
    initTilt();
  }

  /* ──────────────────────────────────────────
     BOOT — run immediately
  ────────────────────────────────────────── */
  initNav();
  initSmoothScroll();
  initFloatCTA();
  initMarquee();
  initScrollVelocity();

})();
