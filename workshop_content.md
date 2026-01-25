# Quantum Cryptography for Hackers

This GitBook is not meant to feel like a research paper or an AI-written crypto blog.  
It’s closer to how **a senior explains things to juniors after a CTF** — casually, with stories, mistakes, and intuition.

If at any point you feel *“oh, that actually makes sense now”*, then it’s doing its job.

---

## How This Book Is Meant to Be Read

You don’t need a physics background.  
You don’t need to love math.

All you need is this mindset:

> *“If this system exists, how can it fail?”*

We’ll talk about cryptography the same way hackers usually do:

- what problem it was trying to solve  
- what assumptions it made  
- how those assumptions break  
- what replaces it  

---

## 1. What Is a Quantum Computer (No Physics Degree Required)

Before we talk about breaking cryptography, we need clarity on  
**what kind of machine a quantum computer actually is**.

A quantum computer is **not** a faster version of your laptop.  
It does not replace classical computers.

Instead, it is a machine designed to solve **specific classes of problems**  
much more efficiently than classical systems.

### Classical vs Quantum (Security-Relevant View)

A classical computer works with **bits**:

- each bit is either `0` or `1`
- operations are deterministic, even when parallelized

A quantum computer works with **qubits**:

- qubits can exist in multiple states until measured
- operations act on probability amplitudes

You do *not* need to understand the physics to understand the impact.

**What matters for security:**

- quantum computers excel at problems involving **period finding**
- they handle **large structured search spaces** extremely well
- many cryptographic assumptions rely on exactly these problems

---

## 2. What Quantum Computers Do in Terms of Security

From a security perspective, quantum computers are **not universally dangerous**.

They do **not**:

- instantly break all encryption
- replace brute-force attacks everywhere

They **do**:

- fundamentally weaken cryptographic systems based on certain mathematical problems

### Cryptographic Assumptions at Risk

Modern public-key cryptography relies on problems that are:

- easy to compute in one direction
- extremely hard to reverse

Examples:

- factoring large integers (RSA)
- discrete logarithms (Diffie–Hellman, ECC)

Quantum algorithms change the cost of reversing these problems.

This is a **threat model change**, not a bug.

---

## 3. Why RSA Is a High-Value Target

RSA is deeply embedded in modern infrastructure.

It is used in:

- TLS handshakes
- certificate authorities
- VPN authentication
- secure email systems

RSA security relies on one core assumption:

> Multiplying two large prime numbers is easy,  
> but factoring their product is infeasible.

As long as factoring remains slow, RSA remains secure.

This assumption held for decades under classical computing.

---

## 4. Breaking RSA: Classical Weaknesses vs Quantum Breaks

### Classical Weaknesses (Already Exploited)

Even today, RSA fails in real-world deployments due to:

- insufficient key sizes
- weak entropy during key generation
- incorrect padding or protocol misuse

These attacks do **not** break RSA mathematically.  
They break how it is implemented and deployed.

This is why RSA is still considered secure  
*when used correctly*.

---

### Quantum Break (Fundamental)

Shor’s algorithm demonstrates that:

- factoring large integers can be done efficiently on a quantum computer

If large-scale quantum computers become practical:

- RSA becomes cryptographically obsolete
- increasing key size will not help

This is a **fundamental break**, not an implementation issue.

---

## 5. Harvest Now, Decrypt Later (HN-DL)

Quantum threats are not limited to the future.

HN-DL attacks make them relevant **today**.

### How the Attack Works

1. An attacker records encrypted traffic now  
2. The data is stored long-term  
3. Decryption happens later using quantum capabilities  

### Why This Matters

Some data loses value quickly.  
Some data must remain secret for decades.

Examples:

- government communications
- medical and genomic data
- long-term intellectual property

For this data, **“secure today” is no longer sufficient**.

---

## 6. Quantum Cryptography: Changing the Defense Model

Quantum cryptography does not attempt to make math harder.

Instead, it relies on **physical principles**  
that cannot be bypassed computationally.

### Core Security Idea

Observing a quantum system necessarily alters it.

This means:

- passive eavesdropping becomes detectable
- secrecy is no longer based on computational limits

Security shifts from **assumptions** to **physical guarantees**.

---

## 7. Quantum Key Distribution (QKD)

QKD is the most mature application of quantum cryptography.

Its purpose is narrow but critical:

- securely distributing cryptographic keys

Important clarifications:

- QKD does **not** encrypt data itself
- it replaces **key exchange**, not symmetric encryption

Once a secure key is shared,  
classical encryption (like AES) is still used.

---

## 8. BB84 Protocol (What Is Actually Happening)

BB84 is the first practical QKD protocol.

At a conceptual level:

- information is encoded using quantum states
- sender and receiver choose random measurement bases
- mismatches reveal eavesdropping

### Why BB84 Is Secure

Security does not depend on hiding the protocol.

It depends on:

- quantum state disturbance
- statistical error detection

Any eavesdropper introduces anomalies  
that cannot be hidden.

---

## 9. Live Demonstration: BB84 in Practice

This section is intentionally practical.

During the workshop:

- demonstrate normal key exchange
- introduce a simulated eavesdropper
- observe how error rates increase

The takeaway is visual and intuitive:

> *Eavesdropping leaves measurable traces.*

---

## 10. Post-Quantum Cryptography (PQC)

Quantum cryptography is powerful  
but difficult to deploy at scale.

PQC provides an alternative:

- quantum-resistant algorithms
- compatibility with existing infrastructure

PQC is already being standardized and tested.

It represents the **most realistic migration path**  
for the modern internet.

---

## 11. Where Attacks Will Actually Happen

Quantum computing will not cause an instant security collapse.

The real vulnerabilities will appear during transition phases:

- incorrect hybrid deployments
- fallback mechanisms
- misunderstood threat models

History shows that migrations  
are where attackers succeed.

---

## Closing Thoughts

Quantum computing changes the assumptions  
cryptography is built on.

It does not remove the need for careful design.  
It **increases** it.

Cryptography has always evolved in response to attacks.  
Quantum computing is simply the next pressure point.

Understanding it early isn’t about hype.  
It’s about being prepared for what breaks next.

If this book helped you think differently about crypto,  
it did its job.
