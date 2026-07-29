# Day 56 — Learnings

## 1. An AI co-pilot can't execute your code for you
A recurring point today: giving Claude a checklist that includes "run every command" doesn't mean Claude runs it — commands and code only execute on your own machine. The actual workflow is: Claude gives exact commands → you run them locally → you paste back the real output → Claude verifies and continues. Understanding this loop clearly prevents a lot of confusion mid-build.

## 2. Don't let a broken confirmation loop silently carry forward
Day 5's results were never actually confirmed in the conversation before Day 6 started. Catching this before finalizing a model (rather than after) avoided potentially building the entire MVP around the wrong model choice.

## 3. Log actual status, not planned status
It would have been easy to write today's GitHub log as "MVP complete" since that was the day's goal. Logging what was *actually* verified — code written, execution still pending — keeps the portfolio trail honest and useful for anyone (including future me) reviewing the repo's real history.

## 4. Explainability doesn't require pretending to know more than you do
For PCA-anonymized features, the explanation logic deliberately gives one honest generic statement instead of fabricating specific-sounding reasons for meaningless anonymized values — accurate uncertainty beats confident-sounding nonsense.
