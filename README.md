import React from "react";

export default function LandingPage() { return ( <div className="min-h-screen bg-white text-gray-800"> {/* Hero Section */} <section className="text-center py-20 bg-gradient-to-r from-indigo-600 to-purple-600 text-white"> <h1 className="text-4xl md:text-6xl font-bold mb-4">DHIBOTAi</h1> <p className="text-lg md:text-2xl max-w-xl mx-auto"> Empowering Bharat with Intelligent AI Agents </p> <a
href="#early-access"
className="inline-block mt-6 px-6 py-3 bg-white text-indigo-600 font-semibold rounded-xl shadow-xl hover:bg-gray-200"
> Join Early Access </a> </section>

{/* Features Section */}
  <section className="py-16 px-4 md:px-20">
    <h2 className="text-3xl font-bold mb-6 text-center">Features</h2>
    <div className="grid md:grid-cols-3 gap-8">
      <div>
        <h3 className="font-semibold text-xl mb-2">Multilingual Support</h3>
        <p>Speak to AI in Hindi, Gujarati, Tamil, and more.</p>
      </div>
      <div>
        <h3 className="font-semibold text-xl mb-2">AI Agents for Every Domain</h3>
        <p>Healthcare, education, manufacturing, and more — all covered.</p>
      </div>
      <div>
        <h3 className="font-semibold text-xl mb-2">Secure & On-Device</h3>
        <p>Edge AI for real-time, private conversations.</p>
      </div>
    </div>
  </section>

  {/* About Section */}
  <section className="py-12 bg-gray-100 px-4 md:px-20">
    <h2 className="text-3xl font-bold mb-4">Why DHIBOTAi?</h2>
    <p className="max-w-3xl text-lg">
      DHIBOTAi is building India’s first Bharat-centric AI ecosystem focused on real-world needs of local industries, education, and healthcare — with modular, multilingual, and ethical AI agents.
    </p>
  </section>

  {/* Call to Action */}
  <section className="text-center py-12 bg-indigo-50">
    <h2 className="text-2xl font-bold mb-4">Be a Part of the AI Revolution</h2>
    <p className="mb-6">Join our early access and be part of the future of Bharat AI.</p>
    <a
      href="#"
      className="inline-block px-6 py-3 bg-indigo-600 text-white font-semibold rounded-xl shadow-xl hover:bg-indigo-700"
    >
      Get Started
    </a>
  </section>
</div>

); }

