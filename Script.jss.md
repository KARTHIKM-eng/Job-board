// script.js - Database Seeding Script (MongoDB)
// Usage: node server/script.js (run from project root)

const mongoose = require('mongoose');
require('dotenv').config();

// Connect to MongoDB
mongoose.connect(process.env.MONGODB_URI, {
  useNewUrlParser: true,
  useUnifiedTopology: true
});

// Job Schema
const jobSchema = new mongoose.Schema({
  title: String,
  company: String,
  location: String,
  salary: Number,
  description: String,
  employerId: mongoose.Schema.Types.ObjectId,
  createdAt: { type: Date, default: Date.now }
});

const Job = mongoose.model('Job', jobSchema);

// Seed sample jobs
const seedJobs = async () => {
  const sampleJobs = [
    {
      title: "Senior React Developer",
      company: "Tech Corp",
      location: "Remote",
      salary: 90000,
      description: "Experienced React developer needed for frontend team"
    },
    {
      title: "Node.js Backend Engineer",
      company: "StartupX",
      location: "New York",
      salary: 85000,
      description: "API development with Node.js and Express"
    }
  ];

  try {
    await Job.deleteMany();
    await Job.insertMany(sampleJobs);
    console.log('Database seeded successfully!');
    process.exit();
  } catch (err) {
    console.error('Seeding error:', err);
    process.exit(1);
  }
};

// Run seeding
seedJobs();
