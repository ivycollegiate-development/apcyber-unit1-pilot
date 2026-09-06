# Checkpoint 1.2 — Password Attacks

Read `topic-1.2/` first. The breach log in that folder is from a (fictional) gaming site, "PixelVault," leaked in a simulated dump. Work through it, then copy this file into `answers/checkpoint-1.2.md` and answer under the headings.

## Question 1
Three PixelVault passwords in the dump are in `data/leaked-top100.txt` (the classic rock-you style list). In your own words: why does password *length* defeat this kind of list attack better than password *complexity* rules?

## Graded response
(your answer here)

---

## Question 2
The dump shows PixelVault stored passwords as plain MD5 hashes with no salt. Using `data/md5-samples.txt`: paste the hash for "letmein123" and explain, in your own words, why a rainbow table makes unsalted MD5 fatal even if the password isn't in the top-100 list.

## Graded response
(your answer here — include the hash value itself in your answer)

---

## Question 3
PixelVault's fix memo proposes: "force users to change passwords every 30 days, minimum 8 chars, must include !@#." Write a 3–4 sentence reply as the security consultant: what's right, what's wrong, and what you'd change instead (cite NIST's actual current guidance from the reading).

## Graded response
(your answer here)
