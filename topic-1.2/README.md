# topic-1.2 — Suspicious Website Logins / Password Attacks

## Big idea
Password attacks are math + psychology. Lists beat lazy passwords; hashing done wrong makes everything worse; length beats complexity rules.

## Lesson map (JuiceMind 1.2, ~55 min)
| Item | Time | Focus |
|---|---|---|
| 1.2.1 How Password Attacks Happen | 10m | Credential stuffing, lists, rate limits |
| 1.2.2 Why Weak Passwords Are Easy to Guess | 10m | Entropy, length vs complexity |
| 1.2.3 How to Strengthen Authentication | 10m | Salting, slow hashes, MFA, passphrases |
| 1.2.4 Review | 5m | |
| 1.2.5 Exit Activity — Password Makeover | 10m | Rewrite weak passwords into strong passphrases |

## Data in this folder
- `data/leaked-top100.txt` — classic wordlist (top-20 abridged)
- `data/md5-samples.txt` — PixelVault breach hashes (unsalted MD5)

## Guided exploration
1. Count how many of the top-20 words follow the "word + digits" pattern. What does that tell you about complexity rules?
2. Look up `letmein123`'s hash in md5-samples.txt. Any online MD5 lookup confirms it instantly — that IS the rainbow-table lesson.

## From the deck (teacher notes, abridged)
- Hook: poll the class — "who has a password with an ! in it?" Then show why that no longer helps.
- Misconception: students conflate hashing with encryption. Fix explicitly: hashing is one-way; encoding ≠ secret.
- NIST SP 800-63B talking points: length > composition rules; no forced periodic rotation; check against breach lists.
- Pacing: hook 5m → entropy demo 10m → PixelVault walkthrough 10m → NIST discussion 10m → checkpoint 10m.
