import React from "react";

// Multi-role portfolio single-file React component
// Tailwind CSS classes assumed to be available in the project
// Replace the placeholder values in the `PROFILE` object with your real details

const PROFILE = {
  name: "ROGERS UGEM ROGERS", // <-- replace with your full name
  age: 19,
  university: "University of Port Harcourt (UniPort)",
  major: "Computer Science",
  title: "CEO & Founder — ROGERS CORP.HOLDINGS | Co-founder — CRE ENTERPRISE",
  location: "Port Harcourt, Nigeria",
  email: "you@example.com",
  phone: "+234 800 000 0000",
  linkedin: "https://linkedin.com/in/your-profile",
  github: "https://github.com/your-username",
  twitter: "https://twitter.com/your-handle",
};

const RoleCard = ({ role, headline, bullets }) => (
  <div className="bg-white/80 dark:bg-slate-900/70 backdrop-blur rounded-2xl shadow-md p-6 flex flex-col gap-4">
    <h3 className="text-xl font-semibold">{role}</h3>
    <p className="text-sm text-slate-600 dark:text-slate-300">{headline}</p>
    <ul className="mt-2 space-y-2 text-sm">
      {bullets.map((b, i) => (
        <li key={i} className="flex gap-3 items-start">
          <span className="font-mono text-xs">•</span>
          <span>{b}</span>
        </li>
      ))}
    </ul>
  </div>
);

export default function Portfolio() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-sky-50 to-white dark:from-slate-900 dark:to-slate-800 text-slate-900 dark:text-slate-100 p-6">
      <header className="max-w-5xl mx-auto flex items-center justify-between py-6">
        <div>
          <h1 className="text-2xl md:text-3xl font-bold tracking-tight">{PROFILE.name}</h1>
          <p className="text-sm text-slate-600 dark:text-slate-300">{PROFILE.title}</p>
        </div>
        <nav className="flex gap-4 items-center">
          <a href="#about" className="text-sm underline-offset-4 hover:underline">About</a>
          <a href="#roles" className="text-sm underline-offset-4 hover:underline">Roles</a>
          <a href="#projects" className="text-sm underline-offset-4 hover:underline">Projects</a>
          <a href="#contact" className="text-sm underline-offset-4 hover:underline">Contact</a>
        </nav>
      </header>

      <main className="max-w-5xl mx-auto space-y-10">
        {/* Hero / About */}
        <section id="about" className="grid grid-cols-1 md:grid-cols-3 gap-6 items-start">
          <div className="md:col-span-2 bg-white/80 dark:bg-slate-900/70 backdrop-blur p-6 rounded-2xl shadow">
            <h2 className="text-2xl font-semibold">About Me</h2>
            <p className="mt-3 text-sm text-slate-700 dark:text-slate-300 leading-relaxed">
              Hi — I’m <strong>{PROFILE.name}</strong> ({PROFILE.age}) — a Computer Science student at <strong>{PROFILE.university}</strong> studying {PROFILE.major}. I wear many hats: businessman,
              forex trader, politician, football coach, and writer. I also lead ROGERS CORP.HOLDINGS as CEO & Founder and co-founded CRE ENTERPRISE.
            </p>

            <div className="mt-4 grid grid-cols-1 sm:grid-cols-3 gap-3 text-sm">
              <div className="p-3 rounded-lg bg-slate-50 dark:bg-slate-800">📍 {PROFILE.location}</div>
              <div className="p-3 rounded-lg bg-slate-50 dark:bg-slate-800">✉️ {PROFILE.email}</div>
              <div className="p-3 rounded-lg bg-slate-50 dark:bg-slate-800">🔗 <a href={PROFILE.linkedin} className="underline">LinkedIn</a></div>
            </div>

            <div className="mt-6 flex gap-3">
              <a href={PROFILE.github} target="_blank" rel="noreferrer" className="px-4 py-2 rounded-lg bg-slate-800 text-white text-sm">View GitHub</a>
              <a href="#contact" className="px-4 py-2 rounded-lg border border-slate-200 dark:border-slate-700 text-sm">Contact</a>
            </div>
          </div>

          <aside className="hidden md:block p-6 rounded-2xl bg-white/60 dark:bg-slate-900/60 shadow flex flex-col gap-4">
            <div>
              <h3 className="text-sm text-slate-500">Quick Facts</h3>
              <ul className="mt-2 text-sm space-y-1">
                <li><strong>Age:</strong> {PROFILE.age}</li>
                <li><strong>Study:</strong> {PROFILE.major} @ {PROFILE.university}</li>
                <li><strong>Companies:</strong> ROGERS CORP.HOLDINGS, CRE ENTERPRISE</li>
                <li><strong>Roles:</strong> Business, Forex, Politics, Sports, Writing</li>
              </ul>
            </div>
            <div>
              <h3 className="text-sm text-slate-500">Availability</h3>
              <p className="text-sm mt-2">Open to partnerships, speaking engagements, advisory roles, and coaching.</p>
            </div>
          </aside>
        </section>

        {/* Roles */}
        <section id="roles">
          <h2 className="text-xl font-semibold mb-4">My Roles & Focus</h2>
          <div className="grid gap-4 grid-cols-1 md:grid-cols-3">
            <RoleCard
              role="Businessman"
              headline="Strategy, partnerships & operations"
              bullets={[
                "Founder-level strategy and operational leadership",
                "Deal-making, partnerships and corporate governance",
                "Business planning, P&L oversight and investor relations",
              ]}
            />

            <RoleCard
              role="Forex Trader"
              headline="Macro analysis, risk management & execution"
              bullets={[
                "Technical & fundamental analysis for FX pairs",
                "Risk-adjusted position sizing and trade journaling",
                "Building automated alerts and simple execution scripts",
              ]}
            />

            <RoleCard
              role="Politician"
              headline="Community-focused leadership & policy advocacy"
              bullets={[
                "Constituency engagement and public speaking",
                "Policy development focused on education and youth empowerment",
                "Coalition building across civic and private sectors",
              ]}
            />

            <RoleCard
              role="Football Coach"
              headline="Tactical coaching & player development"
              bullets={[
                "Youth development, training curricula and match analysis",
                "Tactical planning (positional play, set-pieces)",
                "Team building, discipline and performance tracking",
              ]}
            />

            <RoleCard
              role="Writer"
              headline="Narrative, analysis & thought leadership"
              bullets={[
                "Opinion pieces on economics, governance and sports",
                "Technical write-ups on trading strategies and systems",
                "Regular blog posts and short-form essays",
              ]}
            />

            <RoleCard
              role="CEO / Founder"
              headline="ROGERS CORP.HOLDINGS — strategic leadership"
              bullets={[
                "Built enterprise-level strategy and brand architecture",
                "Directed product, operations and investment decisions",
                "Mentored leadership teams and scaled business lines",
              ]}
            />
          </div>
        </section>

        {/* Projects & Highlights */}
        <section id="projects" className="space-y-4">
          <h2 className="text-xl font-semibold">Selected Projects & Highlights</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div className="p-5 rounded-2xl bg-white/80 dark:bg-slate-900/70 shadow">
              <h3 className="font-semibold">ROGERS CORP.HOLDINGS — Strategic Rollout</h3>
              <p className="text-sm mt-2">Led a cross-functional team to design the holding company structure, launched new business units and secured early-stage partnerships and pilot revenue streams.</p>
              <div className="mt-3 text-sm">
                <strong>My contributions:</strong>
                <ul className="mt-2 list-disc ml-5 space-y-1">
                  <li>Business model design & pilot execution</li>
                  <li>Investor decks and governance framework</li>
                </ul>
              </div>
            </div>

            <div className="p-5 rounded-2xl bg-white/80 dark:bg-slate-900/70 shadow">
              <h3 className="font-semibold">CRE ENTERPRISE — Co-founder Initiative</h3>
              <p className="text-sm mt-2">Co-founded CRE ENTERPRISE to incubate digital-first ventures focused on education & fintech integrations for SMEs.</p>
              <div className="mt-3 text-sm">
                <strong>Impact:</strong>
                <ul className="mt-2 list-disc ml-5 space-y-1">
                  <li>Product-market fit validation & pilot customers</li>
                  <li>Community engagement and SME onboarding</li>
                </ul>
              </div>
            </div>

            <div className="p-5 rounded-2xl bg-white/80 dark:bg-slate-900/70 shadow">
              <h3 className="font-semibold">Forex Strategies — Journal & Signals</h3>
              <p className="text-sm mt-2">Maintained a disciplined trading journal and built reproducible setups for short- and medium-term FX trading. Emphasis on risk management and execution quality.</p>
            </div>

            <div className="p-5 rounded-2xl bg-white/80 dark:bg-slate-900/70 shadow">
              <h3 className="font-semibold">Coaching — Youth Football Program</h3>
              <p className="text-sm mt-2">Designed a seasonal youth training program emphasizing fundamentals, tactical awareness and sportsmanship.</p>
            </div>
          </div>
        </section>

        {/* Callouts / Extras */}
        <section className="grid md:grid-cols-2 gap-4">
          <div className="p-6 rounded-2xl bg-gradient-to-br from-amber-50 to-white shadow">
            <h3 className="font-semibold">Writing & Thought Leadership</h3>
            <p className="text-sm mt-2">I publish short essays and market commentary. Interested parties can request a compendium of writing samples and trading journals.</p>
            <div className="mt-4 text-sm">
              <a href="#contact" className="underline">Request writing samples</a>
            </div>
          </div>

          <div className="p-6 rounded-2xl bg-gradient-to-br from-sky-50 to-white shadow">
            <h3 className="font-semibold">Speaking & Workshops</h3>
            <p className="text-sm mt-2">I run workshops on youth leadership, trading basics, and startup fundraising. Available for talks and panels.</p>
            <div className="mt-4 text-sm">
              <a href="#contact" className="underline">Book me for an event</a>
            </div>
          </div>
        </section>

        {/* Contact */}
        <section id="contact" className="p-6 rounded-2xl bg-white/80 dark:bg-slate-900/70 shadow">
          <h2 className="text-xl font-semibold">Contact</h2>
          <p className="text-sm mt-2">Reach out for partnerships, speaking or coaching enquiries.</p>

          <div className="mt-4 grid grid-cols-1 md:grid-cols-3 gap-4">
            <div className="rounded-lg p-4 bg-slate-50 dark:bg-slate-800">
              <h4 className="font-medium">Email</h4>
              <p className="text-sm mt-1">{PROFILE.email}</p>
            </div>
            <div className="rounded-lg p-4 bg-slate-50 dark:bg-slate-800">
              <h4 className="font-medium">Phone</h4>
              <p className="text-sm mt-1">{PROFILE.phone}</p>
            </div>
            <div className="rounded-lg p-4 bg-slate-50 dark:bg-slate-800">
              <h4 className="font-medium">Social</h4>
              <p className="text-sm mt-1"><a href={PROFILE.linkedin} className="underline">LinkedIn</a> • <a href={PROFILE.github} className="underline">GitHub</a></p>
            </div>
          </div>

          <form className="mt-6 grid grid-cols-1 md:grid-cols-2 gap-4">
            <input type="text" placeholder="Your name" className="p-3 rounded-lg bg-white/90 border" />
            <input type="email" placeholder="Your email" className="p-3 rounded-lg bg-white/90 border" />
            <textarea placeholder="Message" className="p-3 rounded-lg bg-white/90 border md:col-span-2" rows={4} />
            <button type="button" className="md:col-span-2 px-4 py-2 rounded-lg bg-slate-800 text-white">Send Message</button>
          </form>
        </section>

        <footer className="text-center text-sm text-slate-500 py-6">
          <div>Made with care • {PROFILE.name} • {PROFILE.university}</div>
          <div className="mt-2">Replace placeholders in the top of this file with your real name, contact info and links.</div>
        </footer>
      </main>
    </div>
  );
}
