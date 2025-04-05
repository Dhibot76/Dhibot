// Dhibot AI – Admin Dashboard with Dark Mode & Animations // Tech Stack: React, Tailwind, Framer Motion, Axios, FileSaver.js

import React, { useEffect, useState } from "react"; import axios from "axios"; import { saveAs } from "file-saver"; import { motion } from "framer-motion";

function AdminDashboard() { const [loggedIn, setLoggedIn] = useState(false); const [password, setPassword] = useState("");

const [leads, setLeads] = useState([]); const [filteredLeads, setFilteredLeads] = useState([]); const [searchLead, setSearchLead] = useState("");

const [cnc, setCNC] = useState([]); const [filteredCNC, setFilteredCNC] = useState([]); const [searchCNC, setSearchCNC] = useState("");

const [quiz, setQuiz] = useState([]); const [filteredQuiz, setFilteredQuiz] = useState([]); const [searchQuiz, setSearchQuiz] = useState("");

const [pageLead, setPageLead] = useState(1); const [pageCNC, setPageCNC] = useState(1); const [pageQuiz, setPageQuiz] = useState(1); const itemsPerPage = 5;

useEffect(() => { if (loggedIn) { fetchAllData(); } }, [loggedIn]);

useEffect(() => handleSearchLead(), [searchLead, leads]); useEffect(() => handleSearchCNC(), [searchCNC, cnc]); useEffect(() => handleSearchQuiz(), [searchQuiz, quiz]);

const login = () => { if (password === "admin123") setLoggedIn(true); else alert("Wrong password"); };

const fetchAllData = async () => { const resLeads = await axios.get("http://localhost:5000/api/crm/leads"); const resCNC = await axios.get("http://localhost:5000/api/cnc/logs"); const resQuiz = await axios.get("http://localhost:5000/api/quiz/results"); setLeads(resLeads.data); setFilteredLeads(resLeads.data); setCNC(resCNC.data); setFilteredCNC(resCNC.data); setQuiz(resQuiz.data); setFilteredQuiz(resQuiz.data); };

const exportToCSV = (data, filename) => { const csv = [ Object.keys(data[0]).join(","), ...data.map(row => Object.values(row).map(val => "${val}").join(",")) ].join("\n"); const blob = new Blob([csv], { type: "text/csv;charset=utf-8;" }); saveAs(blob, filename); };

const handleSearchLead = () => { const filtered = leads.filter(item => item.name.toLowerCase().includes(searchLead.toLowerCase()) || item.email.toLowerCase().includes(searchLead.toLowerCase()) || item.message.toLowerCase().includes(searchLead.toLowerCase()) ); setFilteredLeads(filtered); setPageLead(1); };

const handleSearchCNC = () => { const filtered = cnc.filter(item => item.command.toLowerCase().includes(searchCNC.toLowerCase()) || item.output.toLowerCase().includes(searchCNC.toLowerCase()) ); setFilteredCNC(filtered); setPageCNC(1); };

const handleSearchQuiz = () => { const filtered = quiz.filter(item => item.username.toLowerCase().includes(searchQuiz.toLowerCase()) ); setFilteredQuiz(filtered); setPageQuiz(1); };

const paginate = (data, page) => data.slice((page - 1) * itemsPerPage, page * itemsPerPage);

if (!loggedIn) { return ( <div className="min-h-screen bg-gray-900 text-white flex items-center justify-center"> <motion.div className="max-w-md w-full p-6 bg-gray-800 rounded shadow text-center" initial={{ opacity: 0, y: -30 }} animate={{ opacity: 1, y: 0 }} > <h2 className="text-2xl font-semibold mb-4">Admin Login</h2> <input type="password" className="border border-gray-600 bg-gray-700 text-white p-2 w-full mb-4 rounded" placeholder="Enter password" value={password} onChange={(e) => setPassword(e.target.value)} /> <button className="bg-blue-600 hover:bg-blue-700 transition px-4 py-2 rounded" onClick={login}>Login</button> </motion.div> </div> ); }

return ( <div className="min-h-screen bg-gray-900 text-white p-6 space-y-8"> <motion.h1 className="text-3xl font-bold text-center" initial={{ opacity: 0 }} animate={{ opacity: 1 }}> Dhibot Admin Dashboard </motion.h1>

<Section ...

