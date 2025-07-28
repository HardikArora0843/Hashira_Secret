Interactive Shamir's Secret Sharing Explorer
An interactive, single-page web application designed to demonstrate and visualize the principles of Shamir's Secret Sharing (SSS), a cryptographic algorithm for securely distributing a secret among a group of participants. This tool allows users to explore how a secret can be reconstructed from a set of "shares," even when some of those shares are corrupted or faulty.

📜 Problem Statement
The core task was to build a fault-tolerant system that could solve for a hidden secret based on a set of distributed shares, as defined in a JSON input file.

You are given a JSON file containing the parameters n (total number of shares) and k (the minimum threshold of shares required for reconstruction). The file also contains n shares, where each share is a point (x, y) on a hidden polynomial of degree k-1. The secret is the constant term of this polynomial (f(0)).

The challenges are:

The y value of each share is encoded as a string in a non-decimal base (e.g., base 2, 16, etc.).

The numbers involved in the calculation can be extremely large, exceeding the limits of standard floating-point data types.

The set of n shares may contain one or more "wrong" or corrupted shares. The system must be able to identify the correct secret by finding a consensus among all possible combinations of shares.

✨ The Solution: An Interactive Web Application
This project solves the problem by providing a hands-on, visual experience within a single HTML file. Instead of just outputting the secret, this web application allows users to:

Visualize the Concept: Understand the high-level idea of splitting a secret into shares.

Run Live Simulations: Select from predefined test cases and execute the secret recovery algorithm in real-time.

Monitor the Process: Watch as the application tests every possible combination of shares, with a progress bar and a live log of calculations.

Analyze the Results: See the final, consensus-based secret displayed clearly, along with a bar chart that visually distinguishes the correct secret from incorrect ones calculated from faulty shares.

Identify Faulty Shares: The application reports which shares were identified as inconsistent with the majority consensus.

🚀 Key Features
Fully Self-Contained: The entire application runs from a single index.html file with no backend or build process required.

Arbitrary-Precision Arithmetic: Utilizes JavaScript's BigInt to handle the massive numbers involved in Lagrange interpolation, ensuring perfect accuracy.

Fault-Tolerant Logic: Implements a combinatorial engine to test all C(n, k) share combinations, successfully filtering out errors to find the true secret.

Dynamic UI: The interface is built with Tailwind CSS for a clean, modern, and responsive design that works on all devices.

Data Visualization: Uses Chart.js to provide clear, visual feedback on the frequency of calculated secrets.

Educational: Includes an expandable "Math Corner" with the Lagrange Interpolation formula rendered beautifully using KaTeX, making the underlying mathematics accessible.

💻 Technology Stack
Frontend: HTML5, JavaScript (ES6+)

Styling: Tailwind CSS

Charting: Chart.js

Math Rendering: KaTeX

▶️ How to Run Locally
No complex setup is required. You can run this application directly in your browser.

Download the Code: Clone this repository or simply download the index.html file.

Open the File: Open the index.html file in any modern web browser (like Google Chrome, Firefox, or Microsoft Edge).

That's it! The application will load, and you can start running the simulations.
