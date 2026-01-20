# X Algo Breakdown: 5 Principles You Need to Know

## 1. Have a Clear POV:
Post 3–5 times/week with a clear stance (helpful insight, strong opinion, lesson learned). Have backbone + have quality. Do not shift your opinions.

Evidence in Code: pheonix/runners.py , user_features_query_hydrator.rs

Shows a clustering based approach around 'cliques'

## 2. Hook fast — nail the first line
This one is obvious, but people choose to ignore it because they don't want to admit its importance and the ego-death it causes 

I.e. the "I wrote great content, it deserves to be seen!" fallacy. Well, the X algorithm doesn't work that way. Since it's attention based, if you didn't pull a high % of people in while scrolling, you'll be stopped.

Evidence: run_ranker.py

A model literally predicts the click/dwell metrics, your tweet is ranked on not how well it would perform on actual users, but on the actual quality of it before it is even given a chance.

Kind of scary, but now you know it's not trial & error or "consistency." If you can't create a good post, you'll be penalized before it's even shown to users.

## 3. Threads or a visual is a must
This keeps people on your post for longer -> the algorithm rewards

Evidence: video_duration_candidate_hydrator.rs, weighted_scroer.rs

Visuals and media get assigned special weights (VQV) which favors these posts by giving them a weightage

## 4. Engage with people in your niche

The model predicts follow_author_score and profile_click_score (signals that reflect users following/visiting profiles), and the pipeline hydrates author metadata (screen name, followers count) — interactions and niche community behavior are thus reflected in training signals and candidate features.

The "be your own niche" is BS for new accounts < 5k followers. Just like successful startups, target a niche and then expand. 

Evidence: candidate . rs, phoenix_scorer.rs

The model and pipeline explicitly use signals tied to author discovery and profile interactions; engaging niche users increases these signals (profile clicks, follows), which the model learns to reward.

## 5. Optimize your profile and amplify your best content

Most people don't do this, but you need to make your profile SEO for X-rich. The algorithm trains on the keywords mentioned in your profile

Your pinned posts, your CTA, everything comes together.

Evidence: gizmoduck_hydrator.rs, weighted_scorer.rs 

Profile fields are hydrated, surfaced, and profile-click/follow signals are used when computing final ranking — optimizing your profile & pinned content can increase profile-click / follow metrics, which the model rewards.

All the code context is fresh in my mind so what else are you curious about? This is so fun to look at, holy shoot
