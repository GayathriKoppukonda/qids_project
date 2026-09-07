# Quantum-Inspired Cyber Threat Detection for Digital Signature Security

A full-stack cybersecurity framework for detecting threats against **teleportation-based Quantum Digital Signature (QDS)** systems using quantum-inspired simulation, projective measurements, statistical analysis, and deterministic security rules.

> **Project Type:** Software
> **Theme:** Blockchain & Cybersecurity
> **Organization:** Egreen Quanta

---

## 📌 Overview

The rapid development of quantum computing creates a long-term security challenge for classical public-key cryptographic algorithms such as RSA and ECC. Quantum algorithms such as Shor's algorithm could make many currently deployed public-key systems vulnerable to sufficiently powerful quantum computers.

This project proposes a **Quantum-Inspired Cyber Threat Detection Framework** for teleportation-based Quantum Digital Signature systems.

Instead of using Artificial Intelligence (AI) or Machine Learning (ML), the system uses:

* Pauli eigenstates
* Bell-state entanglement
* Quantum teleportation
* Pauli correction operations
* Projective measurements
* Statistical verification
* Fixed decision thresholds
* Session and replay protection
* Deterministic threat classification

The project is implemented as a **full-stack web application** with a React frontend and FastAPI backend.

---

## 🎯 Objectives

The major objectives of the project are:

1. Design a threat-detection framework for teleportation-based QDS protocols.
2. Detect signature forgery.
3. Detect signer/verifier impersonation.
4. Detect replay attacks.
5. Detect unauthorized verification attempts.
6. Simulate quantum-channel manipulation.
7. Apply projective measurement and statistical analysis.
8. Provide explainable ACCEPT/REJECT decisions without AI/ML.
9. Build a practical software interface for security monitoring and experimentation.
10. Evaluate the framework using attack simulations and verification metrics.

---

# 🧠 Core Concept

The system models a digital signature verification workflow using quantum states.

The supported Pauli eigenstates are:

```text
Z+ = |0>
Z- = |1>

X+ = (|0> + |1>) / √2
X- = (|0> - |1>) / √2

Y+ = (|0> + i|1>) / √2
Y- = (|0> - i|1>) / √2
```

The system creates an entangled Bell pair and uses a simulated teleportation process to transfer the selected quantum state.

The verifier then performs projective measurements to estimate whether the received state matches the expected signature state.

---

# 🔐 Threat Detection

The framework currently detects the following attack categories:

| Threat                    | Detection Method                                     |
| ------------------------- | ---------------------------------------------------- |
| Forgery                   | Quantum-state mismatch and low measurement agreement |
| Impersonation             | Signer/verifier credential mismatch                  |
| Replay Attack             | Previously used session identifier                   |
| Unauthorized Verification | Verifier authorization check                         |
| Channel Manipulation      | Unexpected quantum-state measurement results         |

---

# 📐 Mathematical Model

For the expected quantum state:

$$
|\psi\rangle
$$

the corresponding projective measurement operator is:

$$
P_\psi = |\psi\rangle \langle\psi|
$$

For an observed state:

$$
|\phi\rangle
$$

the expected verification probability is:

$$
p = \langle\phi|P_\psi|\phi\rangle
$$

or equivalently:

$$
p = |\langle\psi|\phi\rangle|^2
$$

For repeated measurements:

$$
r = \frac{k}{N}
$$

where:

* `k` = number of successful measurements
* `N` = total measurements
* `r` = observed success rate

The framework then calculates a conservative statistical lower bound:

$$
LB = r - z\sqrt{\frac{r(1-r)}{N}}
$$

The prototype uses a fixed threshold:

$$
LB \ge 0.90
$$

to accept a signature.

This is a deterministic statistical rule and **does not involve machine learning**.

---

# 🏗️ System Architecture

```text
                 ┌─────────────────────┐
                 │   React Frontend    │
                 │                     │
                 │ Dashboard           │
                 │ Signature Creation  │
                 │ Verification        │
                 │ Attack Simulation   │
                 └──────────┬──────────┘
                            │
                         REST API
                            │
                            ▼
                 ┌─────────────────────┐
                 │   FastAPI Backend   │
                 │                     │
                 │ Authentication      │
                 │ Signature Service   │
                 │ Verification API    │
                 │ Replay Protection   │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   QDS Protocol      │
                 │      Layer          │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Quantum Simulator   │
                 │                     │
                 │ Bell States         │
                 │ Teleportation       │
                 │ Pauli Corrections   │
                 │ Projectors          │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Threat Detector     │
                 │                     │
                 │ Forgery             │
                 │ Impersonation       │
                 │ Replay              │
                 │ Unauthorized Access │
                 │ Channel Attack      │
                 └──────────┬──────────┘
                            │
                            ▼
                     ACCEPT / REJECT
```

---

# 💻 Technology Stack

## Frontend

* React
* Vite
* JavaScript
* HTML5
* CSS3

## Backend

* Python
* FastAPI
* Uvicorn
* Pydantic

## Quantum Simulation

* Python
* NumPy
* State-vector simulation
* Matrix operations

## Testing

* Python `unittest`

---

# 📁 Project Structure

```text
qids_project/
│
├── backend/
│   ├── main.py
│   └── requirements.txt
│
├── frontend/
│   ├── package.json
│   ├── index.html
│   └── src/
│       ├── main.jsx
│       └── styles.css
│
├── src/
│   ├── quantum.py
│   ├── protocol.py
│   ├── detector.py
│   ├── attacks.py
│   └── main.py
│
├── tests/
│   └── test_project.py
│
├── data/
│
├── docs/
│
├── all_in_one.py
├── requirements.txt
└── README.md
```

---

# 🚀 Installation

## Prerequisites

Install:

* Python 3.10+
* Node.js 18+
* npm
* VS Code

---

## Backend Setup

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd qids_project
```

Create a virtual environment:

### Windows

```powershell
python -m venv .venv
.venv\Scripts\activate
```

### Linux/macOS

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install Python dependencies:

```bash
python -m pip install -r requirements.txt
```

---

# ▶️ Run Backend

From the project root:

```bash
python -m uvicorn backend.main:app --reload
```

Backend:

```text
http://127.0.0.1:8000
```

Interactive API documentation:

```text
http://127.0.0.1:8000/docs
```

---

# ▶️ Run Frontend

Open a second terminal:

```bash
cd frontend
npm install
npm run dev
```

Open:

```text
http://localhost:5173
```

---

# 🧪 Run the Quantum/QDS Demo

From the project root:

```bash
python -m src.main demo
```

This demonstrates legitimate quantum-state transmission and verification.

---

# ⚔️ Run Attack Simulations

```bash
python -m src.main attacks
```

The framework simulates:

```text
LEGITIMATE
FORGERY
IMPERSONATION
REPLAY
CHANNEL MANIPULATION
```

Example:

```text
LEGITIMATE           → ACCEPT
FORGERY              → REJECT
IMPERSONATION        → REJECT
REPLAY_FIRST         → ACCEPT
REPLAY_SECOND        → REJECT
CHANNEL_MANIPULATION → REJECT
```

---

# ✅ Run Tests

```bash
python -m unittest discover -s tests -v
```

The automated test suite covers:

* Teleportation state recovery
* Legitimate signature verification
* Forgery rejection
* Replay rejection
* Impersonation rejection

---

# 🔄 Application Workflow

```text
1. User selects a message
        ↓
2. Signer selects a Pauli eigenstate
        ↓
3. Signature packet is generated
        ↓
4. Bell pair is prepared
        ↓
5. Quantum teleportation is simulated
        ↓
6. Pauli corrections are applied
        ↓
7. Verifier performs projective measurements
        ↓
8. Measurement statistics are calculated
        ↓
9. Security rules are evaluated
        ↓
10. Threat is classified
        ↓
11. ACCEPT / REJECT result shown
```

---

# 🛡️ Security Features

### 1. Forgery Detection

The detector compares the received quantum state against the expected state using projective measurement probability.

Incorrect states reduce the verification confidence and can cause rejection.

### 2. Impersonation Detection

Signer and verifier information is bound to the verification workflow.

Unexpected identities are rejected.

### 3. Replay Protection

Every signature session contains a unique session identifier.

After a successful verification, the session is marked as used.

A subsequent attempt with the same session is identified as a replay attack.

### 4. Unauthorized Verification

Only authorized verifier identities are allowed to perform the verification operation.

### 5. Channel Manipulation

The framework simulates manipulated quantum states and observes the effect through projective measurement statistics.

---

# 📊 Performance Metrics

The framework can be evaluated using:

### Verification Accuracy

$$
Accuracy = \frac{Correct\ Decisions}{Total\ Decisions}
$$

### False Acceptance Rate

$$
FAR = \frac{False\ Acceptances}{Total\ Attack\ Attempts}
$$

### False Rejection Rate

$$
FRR = \frac{False\ Rejections}{Total\ Legitimate\ Attempts}
$$

### Measurement Success Rate

$$
SuccessRate = \frac{Successful\ Measurements}{Total\ Measurements}
$$

### Verification Time

The application can measure the time required to:

```text
Create signature
↓
Perform quantum simulation
↓
Perform measurements
↓
Generate security decision
```

---

# 🧪 Example Experiment

A simple experiment can compare legitimate and manipulated states.

### Legitimate case

```text
Expected state: X+
Received state: X+
Measurement success: High
Decision: ACCEPT
```

### Forgery case

```text
Expected state: X+
Received state: Z+
Measurement agreement: Reduced
Decision: REJECT
```

### Replay case

```text
First verification:
ACCEPT

Second verification with same session:
REJECT
Threat: REPLAY
```

---

# 📈 Future Enhancements

Possible future improvements include:

* Integration with real quantum hardware
* Qiskit-based circuit execution
* Real QKD/QDS protocol implementations
* Database-backed audit logging
* JWT/OAuth authentication
* Redis-based session/replay storage
* WebSocket-based live monitoring
* Cryptographic key management
* Multi-verifier QDS support
* Advanced finite-size statistical analysis
* Formal security verification
* Docker deployment
* Cloud deployment
* Blockchain-based signature audit trails

---

# ⚠️ Limitations

This project is a **software simulation and research prototype**.

It does not claim that NumPy simulation is equivalent to a physical quantum communication channel.

A production QDS deployment would require additional considerations including:

* Physical quantum devices
* Realistic noise models
* Quantum channel characterization
* Authenticated classical communication
* Finite-size security analysis
* Device imperfections
* Side-channel analysis
* Formal protocol security proofs

Therefore, the project should be considered a **demonstration of a quantum-inspired threat-detection architecture**.

---

# 🎓 Academic Relevance

This project combines several areas of computer science and cybersecurity:

```text
Quantum Computing
       +
Cybersecurity
       +
Digital Signatures
       +
Statistical Analysis
       +
Full-Stack Software Engineering
```

It demonstrates how quantum concepts can be transformed into practical software security mechanisms without requiring artificial intelligence or machine learning.

---

# 👨‍💻 Authors

**Student Project**

Organization: **Egreen Quanta**

Department: **Egreen Quanta**

Category: **Software**

Theme: **Blockchain & Cybersecurity**

---

# 📜 License

This project is intended for educational and research purposes.

Add an appropriate open-source license before public distribution, such as MIT, Apache-2.0, or another license compatible with your project requirements.

---

# ⭐ Acknowledgement

This project was developed as an academic software prototype exploring quantum-inspired security monitoring for future digital-signature systems.

---

# 📚 References

* NIST — Post-Quantum Cryptography
* NIST — Post-Quantum Cryptography Standards
* Quantum information and quantum teleportation literature
* Research literature on Quantum Digital Signatures
* FastAPI Documentation
* React Documentation
* NumPy Documentation
