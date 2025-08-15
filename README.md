import { useState } from "react";

// ====== HOW TO DEPLOY ON GITHUB PAGES ======
// 1) Create repo named <your-username>.github.io
// 2) Add this file as src/App.jsx in a React/Vite app OR paste into Codesandbox and export.
//    Quickest: use Vite -> React + JS; replace App.jsx with this file.
// 3) Build & deploy: either
//    a) Use GitHub Actions (Vite deploy to gh-pages), or
//    b) If you prefer plain HTML, ask me for a static HTML version and I'll generate it.
// -----------------------------------------------------------

export default function App() {
  const [dark, setDark] = useState(true);

  // ====== EDIT YOUR INFO HERE ======
  const me = {
    name: "Your Name",
    tagline: "PhD — Machine Learning & Time Series",
    location: "Baton Rouge, LA, USA",
    email: "you@lsu.edu",
    scholar: "https://scholar.google.com/",
    github: "https://github.com/your-username",
    linkedin: "https://www.linkedin.com/in/your-handle/",
    cvUrl: "/assets/CV.pdf", // put a CV at /public/assets/CV.pdf
  };

  // Example publications (replace with yours)
  const pubs = [
    {
      authors: "Zhao, T., Chen, X., Sun, M.",
      year: "2025",
      title:
        "Enhancing Time Series Forecasting via Multi-Level Text Alignment with Large Language Models",
      venue: "Proc. DASFAA",
      link: "#",
      note: "May 2025",
    },
    {
      authors: "Zhao, T., Sun, M., Hao, W., Chen, X., Zhou, X.",
      year: "2025",
      title:
        "Pruning and Malicious Injection: A Retraining-Free Backdoor Attack on Transformer Models",
      venue: "arXiv preprint",
      link: "#",
      note: "",
    },
    {
      authors:
        "Chen, X., Zhou, X., Zhang, H., Sun, M., Zhao, T.",
      year: "2025",
      title:
        "Joint Device and Training Scheduling for Wireless Federated Learning",
      venue: "IEEE Internet of Things Journal (In Press)",
      link: "#",
      note: "",
    },
    {
      authors:
        "Chen, X., Zhou, X., Zhang, H., Sun, M., Zhao, T.",
      year: "2024",
      title:
        "Cost-Effective Federated Learning: A Unified Approach to Device and Training Scheduling",
      venue: "Proc. IEEE ICC",
      link: "#",
      note: "June 2024",
    },
  ];

  const projects = [
    {
      name: "Deceleration Index Toolkit",
      desc: "Python utilities to compute DI from 1080 Motion CSV (accel/decel profiling).",
      link: "https://github.com/your-username/deceleration-index",
      tags: ["Python", "Sports Science", "Data Analysis"],
    },
    {
      name: "Edge AI Pruning & Quantization",
      desc: "Lightweight inference on embedded devices; 30% latency reduction with minimal accuracy loss.",
      link: "https://github.com/your-username/edge-ai-toolkit",
      tags: ["PyTorch", "ONNX", "Quantization"],
    },
  ];

  return (
    <div className={dark ? "min-h-screen bg-zinc-950 text-zinc-100" : "min-h-screen bg-white text-zinc-900"}>
      <div className="max-w-4xl mx-auto px-5 py-10">
        {/* Header */}
        <header className="flex items-start justify-between gap-4">
          <div>
            <h1 className="text-3xl sm:text-4xl font-bold tracking-tight">{me.name}</h1>
            <p className="mt-1 text-zinc-400">{me.tagline}</p>
            <p className="mt-1 text-zinc-400">{me.location}</p>
            <div className="mt-3 flex flex-wrap gap-3 text-sm">
              <a className="underline underline-offset-2" href={`mailto:${me.email}`}>{me.email}</a>
              <a className="underline underline-offset-2" href={me.scholar} target="_blank">Google Scholar</a>
              <a className="underline underline-offset-2" href={me.github} target="_blank">GitHub</a>
              <a className="underline underline-offset-2" href={me.linkedin} target="_blank">LinkedIn</a>
              <a className="underline underline-offset-2" href={me.cvUrl} target="_blank">CV (PDF)</a>
            </div>
          </div>
          <button
            onClick={() => setDark(v => !v)}
            className="rounded-2xl border px-3 py-2 text-sm hover:bg-zinc-800/50"
            aria-label="Toggle theme"
          >
            {dark ? "Light" : "Dark"} mode
          </button>
        </header>

        {/* About */}
        <section className="mt-10">
          <h2 className="text-xl font-semibold">About</h2>
          <p className="mt-3 leading-7 text-zinc-300">
            I am a PhD focusing on machine learning, time series forecasting, and efficient deep learning for
            embedded systems. My recent work includes LLM-aided temporal representation learning and
            backdoor robustness in Transformers. I enjoy translating research into production-ready tools.
          </p>
        </section>

        {/* Publications */}
        <section className="mt-10">
          <h2 className="text-xl font-semibold">Selected Publications</h2>
          <ul className="mt-4 space-y-4">
            {pubs.map((p, i) => (
              <li key={i} className="rounded-2xl border border-zinc-800 p-4">
                <div className="text-sm text-zinc-400">{p.year}</div>
                <div className="mt-1 font-medium">
                  {p.title}
                </div>
                <div className="mt-1 text-sm text-zinc-300">
                  {/* Bold your name */}
                  {p.authors.replace("Zhao, T.", "**Zhao, T.**")}
                </div>
                <div className="mt-1 text-sm italic text-zinc-400">{p.venue}{p.note ? ` — ${p.note}` : ""}</div>
                {p.link && p.link !== "#" && (
                  <a className="mt-2 inline-block underline underline-offset-2 text-sm" href={p.link} target="_blank">link</a>
                )}
              </li>
            ))}
          </ul>
          <p className="mt-3 text-sm text-zinc-400">
            Full list on <a className="underline" href={me.scholar} target="_blank">Google Scholar</a>.
          </p>
        </section>

        {/* Projects */}
        <section className="mt-10">
          <h2 className="text-xl font-semibold">Projects</h2>
          <div className="mt-4 grid sm:grid-cols-2 gap-4">
            {projects.map((prj, i) => (
              <a key={i} href={prj.link} target="_blank" className="rounded-2xl border border-zinc-800 p-4 hover:bg-zinc-800/40">
                <div className="font-medium">{prj.name}</div>
                <div className="mt-1 text-sm text-zinc-300">{prj.desc}</div>
                <div className="mt-2 flex flex-wrap gap-2 text-xs text-zinc-400">
                  {prj.tags.map((t) => (
                    <span key={t} className="rounded-full border px-2 py-0.5">{t}</span>
                  ))}
                </div>
              </a>
            ))}
          </div>
        </section>

        {/* Contact */}
        <section className="mt-10 mb-16">
          <h2 className="text-xl font-semibold">Contact</h2>
          <p className="mt-2 text-zinc-300">
            For collaborations or questions, email me at <a className="underline" href={`mailto:${me.email}`}>{me.email}</a>.
          </p>
        </section>
      </div>
    </div>
  );
}
# ztb-35.github.io
