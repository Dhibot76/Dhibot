import React from "react";
import { motion } from "framer-motion";

// Custom Button Component
const Button = ({ children, className = "", onClick }) => {
  return (
    <button
      className={`px-6 py-3 rounded-lg font-medium hover:bg-opacity-80 ${className}`}
      onClick={onClick}
    >
      {children}
    </button>
  );
};

// Home Page Component
export default function Home() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-indigo-700 to-purple-600 text-white flex flex-col">
      {/* Header Section */}
      <header className="flex justify-between items-center p-5">
        <h1 className="text-3xl font-extrabold">Dhibot AI</h1>
        <nav className="space-x-4">
          <Button className="bg-purple-800">Home</Button>
          <Button className="bg-purple-800">Features</Button>
          <Button className="bg-purple-800">Pricing</Button>
          <Button className="bg-purple-800">Blog</Button>
          <Button className="bg-purple-800">Contact</Button>
        </nav>
      </header>

      {/* Hero Section */}
      <main className="flex-grow flex flex-col items-center justify-center">
        <motion.h1
          initial={{ scale: 0.9 }}
          animate={{ scale: 1 }}
          transition={{ duration: 0.5 }}
          className="text-6xl font-extrabold mb-4"
        >
          Welcome to Dhibot AI
        </motion.h1>
        <p className="text-xl mb-6 text-center max-w-xl">
          Transforming industries with Hyper-Personalized AI Solutions, Real-Time Multilingual Support, and more!
        </p>
        <Button className="bg-blue-500">Get Started</Button>
      </main>

      {/* Features Section */}
      <section className="p-10 bg-white text-black">
        <h2 className="text-4xl font-bold text-center mb-8">Our Features</h2>
        <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <FeatureCard
            title="Hyper-Personalization"
            description="Tailored AI experiences for every user."
          />
          <FeatureCard
            title="Domain Expertise"
            description="Custom solutions for business-specific needs."
          />
          <FeatureCard
            title="Real-Time Translation"
            description="Multilingual communication made seamless."
          />
          <FeatureCard
            title="Emotional Intelligence"
            description="AI that understands and empathizes."
          />
        </div>
      </section>

      {/* Footer Section */}
      <footer className="p-5 bg-purple-800 text-center">
        <p>&copy; 2025 Dhibot AI. All Rights Reserved.</p>
      </footer>
    </div>
  );
}

// Feature Card Component
const FeatureCard = ({ title, description }) => {
  return (
    <div className="p-5 border rounded-lg hover:shadow-lg transition">
      <h3 className="text-2xl font-bold mb-2">{title}</h3>
      <p>{description}</p>
    </div>
  );
};