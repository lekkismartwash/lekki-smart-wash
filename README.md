import React from "react";
import { motion } from "framer-motion";
import { Phone, Mail, Instagram, Truck } from "lucide-react";

// This is a single-file React component styled with Tailwind CSS.
// Exports a default page component you can drop into a Next.js or CRA app
// Tailwind must be configured in the project. Framer Motion and lucide-react should be installed.

export default function LekkiSmartWash() {
  const whatsapp = "https://wa.me/2347077673997";

  return (
    <div className="min-h-screen bg-gradient-to-b from-white via-sky-50 to-white text-slate-800 antialiased">
      <header className="max-w-6xl mx-auto px-6 py-6 flex items-center justify-between">
        <div className="flex items-center gap-3">
          <div className="w-12 h-12 rounded-2xl bg-sky-500 flex items-center justify-center text-white font-bold text-lg">LS</div>
          <div>
            <h1 className="text-xl font-bold">Lekki Smart Wash</h1>
            <p className="text-sm text-slate-500">We Wash. You Relax.</p>
          </div>
        </div>

        <nav className="hidden md:flex items-center gap-6 text-sm">
          <a href="#services" className="hover:text-sky-600">Services</a>
          <a href="#how" className="hover:text-sky-600">How it works</a>
          <a href="#pricing" className="hover:text-sky-600">Pricing</a>
          <a href="#testimonials" className="hover:text-sky-600">Testimonials</a>
          <a href={whatsapp} className="inline-flex items-center gap-2 bg-sky-600 text-white px-4 py-2 rounded-lg shadow">Book Pickup</a>
        </nav>

        <div className="md:hidden">
          <a href={whatsapp} className="inline-flex items-center gap-2 bg-sky-600 text-white px-3 py-2 rounded-lg shadow-sm text-sm">Book</a>
        </div>
      </header>

      <main className="max-w-6xl mx-auto px-6">
        {/* Hero */}
        <section className="grid md:grid-cols-2 gap-8 items-center mt-6">
          <motion.div initial={{ x: -30, opacity: 0 }} animate={{ x: 0, opacity: 1 }} transition={{ duration: 0.5 }}>
            <h2 className="text-4xl md:text-5xl font-extrabold leading-tight">We Wash. You Relax.</h2>
            <p className="mt-4 text-lg text-slate-600">Pickup, expert cleaning, and delivery — made simple for busy Lagos life. Fresh clothes, on time, every time.</p>

            <div className="mt-6 flex flex-wrap gap-3">
              <a href={whatsapp} className="inline-flex items-center gap-2 bg-sky-600 text-white px-4 py-3 rounded-lg shadow">Schedule Pickup</a>
              <a href="#pricing" className="inline-flex items-center gap-2 border border-slate-200 px-4 py-3 rounded-lg">See Pricing</a>
            </div>

            <div className="mt-8 grid grid-cols-2 gap-3 text-sm text-slate-500">
              <div className="flex items-center gap-3">
                <Truck className="w-5 h-5 text-sky-500" />
                <div>
                  <div className="font-semibold">Free pickup</div>
                  <div className="text-xs">On orders above ₦5,000</div>
                </div>
              </div>

              <div className="flex items-center gap-3">
                <Phone className="w-5 h-5 text-sky-500" />
                <div>
                  <div className="font-semibold">Fast turnaround</div>
                  <div className="text-xs">Same-day & next-day options</div>
                </div>
              </div>
            </div>
          </motion.div>

          <motion.div initial={{ x: 30, opacity: 0 }} animate={{ x: 0, opacity: 1 }} transition={{ duration: 0.5 }} className="flex items-center justify-center">
            <div className="w-full md:w-4/5 bg-white p-6 rounded-2xl shadow-md">
              <img alt="folded clothes" src="https://images.unsplash.com/photo-1540574163026-643ea20ade25?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" className="w-full rounded-lg object-cover h-56" />

              <div className="mt-4">
                <h3 className="font-semibold">Doorstep laundry made simple</h3>
                <p className="text-sm text-slate-500 mt-1">Book through WhatsApp or our contact form — we collect, clean, and return with care.</p>
              </div>
            </div>
          </motion.div>
        </section>

        {/* Services */}
        <section id="services" className="mt-16">
          <h3 className="text-2xl font-bold">Our Services</h3>
          <p className="text-slate-500 mt-2">Everything from everyday washes to special-care garments.</p>

          <div className="mt-6 grid md:grid-cols-3 gap-6">
            <ServiceCard title="Wash, Dry & Fold" desc="Perfect for everyday clothing — fast, fresh and folded." badge="Popular" />
            <ServiceCard title="Dry Cleaning & Delicates" desc="Suits, dresses, and delicate fabrics handled with expert care." />
            <ServiceCard title="Pickup & Delivery" desc="Doorstep collection and return. Schedule at your convenience." />
          </div>
        </section>

        {/* How it works */}
        <section id="how" className="mt-16 bg-white p-6 rounded-2xl shadow-sm">
          <h3 className="text-2xl font-bold">How it works</h3>
          <div className="mt-6 grid md:grid-cols-3 gap-6">
            <Step number={1} title="Book a Pickup" desc="Message us on WhatsApp or use the online form." />
            <Step number={2} title="We Collect" desc="Our team picks up your laundry at the scheduled time." />
            <Step number={3} title="Clean & Deliver" desc="Expert cleaning, folded and returned to your doorstep." />
          </div>
        </section>

        {/* Pricing */}
        <section id="pricing" className="mt-16">
          <h3 className="text-2xl font-bold">Simple pricing</h3>
          <p className="text-slate-500 mt-2">Transparent, affordable plans — no surprises.</p>

          <div className="mt-6 grid md:grid-cols-3 gap-6">
            <PriceCard title="Basic" price="₦1,200/kg" perks={["Wash & fold","3-4 day turnaround","Eco detergent"]} />
            <PriceCard title="Express" price="₦1,800/kg" perks={["Same-day option","Priority processing","Free pickup"]} featured />
            <PriceCard title="Premium" price="₦2,500/kg" perks={["Hand finish","Delicate care","Packaging included"]} />
          </div>
        </section>

        {/* Testimonials */}
        <section id="testimonials" className="mt-16">
          <h3 className="text-2xl font-bold">What customers say</h3>
          <div className="mt-6 grid md:grid-cols-3 gap-6">
            <Testimonial name="Amaka" text="Fast, friendly service. Pickup was on time and clothes came back smelling great!" />
            <Testimonial name="Tunde" text="Saved me so much time. Perfect for busy weeks at the office." />
            <Testimonial name="Ngozi" text="My wedding dress was returned spotless. Highly recommend their delicate care." />
          </div>
        </section>

        {/* CTA */}
        <section className="mt-16 bg-sky-600 text-white p-8 rounded-2xl flex flex-col md:flex-row items-center justify-between gap-4">
          <div>
            <h4 className="text-2xl font-bold">Ready to relax?</h4>
            <p className="mt-2 text-slate-100">Book a pickup now and get ₦500 off your first order.</p>
          </div>
          <div className="flex gap-3">
            <a href={whatsapp} className="inline-flex items-center gap-2 bg-white text-sky-600 px-4 py-3 rounded-lg font-semibold">Book via WhatsApp</a>
            <a href="#pricing" className="inline-flex items-center gap-2 border border-white/30 px-4 py-3 rounded-lg">See Plans</a>
          </div>
        </section>

        {/* Footer */}
        <footer className="mt-12 py-8 text-sm text-slate-600">
          <div className="max-w-6xl mx-auto flex flex-col md:flex-row items-center justify-between gap-4">
            <div>
              <div className="font-semibold">Lekki Smart Wash</div>
              <div className="mt-1">Serving Lekki & nearby areas</div>
            </div>

            <div className="flex items-center gap-4">
              <a href={whatsapp} className="flex items-center gap-2 hover:text-sky-600"><Phone className="w-4 h-4"/> +234 707 767 3997</a>
              <a href="#" className="flex items-center gap-2 hover:text-sky-600"><Instagram className="w-4 h-4"/> @lekkismartwash</a>
              <a href="#" className="flex items-center gap-2 hover:text-sky-600"><Mail className="w-4 h-4"/> hello@lekkismartwash.ng</a>
            </div>
          </div>
        </footer>
      </main>
    </div>
  );
}

// --- Small UI pieces ---
function ServiceCard({ title, desc, badge }) {
  return (
    <div className="bg-white p-5 rounded-xl shadow-sm">
      <div className="flex items-start justify-between">
        <div>
          <h4 className="font-semibold">{title}</h4>
          <p className="text-sm text-slate-500 mt-2">{desc}</p>
        </div>
        {badge && <div className="text-xs bg-sky-100 text-sky-700 px-2 py-1 rounded-md">{badge}</div>}
      </div>
    </div>
  );
}

function Step({ number, title, desc }) {
  return (
    <div className="flex flex-col items-start gap-3">
      <div className="w-12 h-12 rounded-xl bg-sky-50 flex items-center justify-center font-bold text-sky-600">{number}</div>
      <div>
        <h5 className="font-semibold">{title}</h5>
        <p className="text-sm text-slate-500 mt-1">{desc}</p>
      </div>
    </div>
  );
}

function PriceCard({ title, price, perks, featured }) {
  return (
    <div className={`${featured ? "border-sky-500 shadow-lg" : "border-slate-100"} bg-white p-6 rounded-xl border` }>
      <div className="flex items-center justify-between">
        <div>
          <div className="text-sm text-slate-500">{title}</div>
          <div className="text-2xl font-bold mt-2">{price}</div>
        </div>
        {featured && <div className="text-xs px-2 py-1 bg-sky-600 text-white rounded">Most popular</div>}
      </div>
      <ul className="mt-4 space-y-2 text-sm text-slate-600">
        {perks.map((p) => (
          <li key={p}>• {p}</li>
        ))}
      </ul>
      <div className="mt-6">
        <a href="https://wa.me/2347077673997" className="inline-block w-full text-center px-4 py-3 rounded-lg bg-sky-600 text-white font-semibold">Choose plan</a>
      </div>
    </div>
  );
}

function Testimonial({ name, text }) {
  return (
    <div className="bg-white p-5 rounded-xl shadow-sm">
      <p className="text-slate-600">“{text}”</p>
      <div className="mt-4 font-semibold">{name}</div>
    </div>
  );
}
