/* style.css - Global Styles for Job Board */
:root {
  --primary-color: #2563eb;   /* Blue */
  --secondary-color: #3b82f6; /* Lighter Blue */
  --text-color: #1f2937;      /* Dark Gray */
  --background-light: #f3f4f6;
  --success-color: #22c55e;   /* Green */
  --error-color: #ef4444;     /* Red */
}

/* Base Styles */
body {
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--text-color);
  margin: 0;
  padding: 0;
  line-height: 1.6;
}

/* Header */
.header {
  background: white;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  padding: 1rem;
  position: sticky;
  top: 0;
  z-index: 1000;
}

.nav {
  display: flex;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
}

.logo {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--primary-color);
}

/* Job Listings Grid */
.job-grid {
  display: grid;
  gap: 1.5rem;
  padding: 2rem 1rem;
  max-width: 1200px;
  margin: 0 auto;
}

.job-card {
  background: white;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  transition: transform 0.2s;
}

.job-card:hover {
  transform: translateY(-2px);
}

/* Forms */
.auth-form {
  max-width: 400px;
  margin: 2rem auto;
  padding: 2rem;
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.input-group {
  margin-bottom: 1.5rem;
}

input, textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #e5e7eb;
  border-radius: 4px;
  font-size: 1rem;
}

button {
  background: var(--primary-color);
  color: white;
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: 600;
}

button:hover {
  background: var(--secondary-color);
}

/* Dashboard Tables */
.dashboard-table {
  width: 100%;
  border-collapse: collapse;
  background: white;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.dashboard-table th,
.dashboard-table td {
  padding: 1rem;
  text-align: left;
  border-bottom: 1px solid #e5e7eb;
}

/* Mobile Responsiveness */
@media (max-width: 768px) {
  .job-grid {
    grid-template-columns: 1fr;
  }

  .nav {
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  .auth-form {
    margin: 1rem;
    padding: 1rem;
  }
}

/* Utility Classes */
.text-success { color: var(--success-color); }
.text-error { color: var(--error-color); }
.alert {
  padding: 1rem;
  border-radius: 4px;
  margin: 1rem 0;
}
.alert-success {
  background: #dcfce7;
  border: 1px solid var(--success-color);
}
.alert-error {
  background: #fee2e2;
  border: 1px solid var(--error-color);
}
