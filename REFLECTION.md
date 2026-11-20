# Reflection

Name: Anapat

Answer each question in 2–3 sentences.

**1. Which antipatterns from the lecture did `train_all.py` show? Point to the lines.**

> All steps are in one long script (lines 14–45), so cannot test one step alone. File name, date format and tree depth are fixed in code (lines 15, 19, 35). Old experiment still there but not used (lines 27–31), and model is saved even when it is bad (lines 43–45).

**2. Suppose there were no test and no evaluation gate. What would have happened when the 2026 batch arrived? Think about both the crash and the missing `sqft` values.**

> New date format still crashes the script, but if only the dates get fixed, 12 homes with no size go through. Model trains on them with no error and still stays under the $50,000 limit, so nobody notices. Without gate, bad model also gets saved and shown to users.

**3. In the real marketplace, which non-ML parts of the system should trigger this pipeline or feed it data?**

> Sales system should send new sales and start a run when they come in, or on schedule. Listing form should make sellers fill in home size, because missing values come from there. Code change should also start a run, and when our prices drift away from real sale prices, it should start retrain.
