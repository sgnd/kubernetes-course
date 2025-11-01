# Kubernetes Resources: Cheatsheet & Interview Questions

A compact, practical collection of Kubernetes study resources: a hands-on cheatsheet of common `kubectl` workflows and an organized set of interview questions to guide your learning and review.

Contents
- `CHEATSHEET.md` — Quick `kubectl` commands grouped by workflow with examples and tips.
- `INTERVIEW.md` — Topic-organized interview questions from fundamentals to advanced topics.
- `LICENSE` — Project license.

Get started
1. Open `CHEATSHEET.md` and try the commands on a lab cluster (kind, minikube, or a managed sandbox).
2. Use `INTERVIEW.md` to structure mock interviews or convert questions into flashcards.

How to contribute
- Found an error or want to add commands/questions? Please open a Pull Request. Include a short rationale and an example use-case for new entries.
- Keep entries concise and prefer commands that work with modern Kubernetes versions (1.20+).

Notes & tips
- Use `kubectl explain <resource>` to learn object fields.
- For scripting and automation, prefer `-o jsonpath` or `-o json` for machine-parsable output.
- Consider converting long command sequences into small helper scripts or `kubectl` plugins.

License
This project is licensed under the MIT License. See `LICENSE` for details.
