## Lab 3

1. Which model is the best? Can we prove it?
   Yes, now we can. In the MLflow interface I sorted the runs by f1: trial-1 and trial-3 have the same score (0.889) and trial-2 is much lower (0.333). Everything is saved so I can show it. Between the two I keep trial-3 because it gives the same result without using the salary.

2. Can we give back exactly the model of trial 1?
   Yes. In Lab 1 model.pkl was overwritten every time, but now each run keeps its own model. With the run id we can reload it (load_model) without training again. I tested it with reload_model.py.

3. Can a classmate reproduce my work?
   Not completely. He can get the code from GitHub and see the parameters and library versions in each run. But he won't have my runs (mlruns is not on Git) and his environment can be different. We will fix this later with Docker.

## Lab 4

1. How do we choose the official model?
   We use the "champion" alias in the Registry. We don't need the run id anymore, we just load models:/churn-model@champion. For me it points to version 1 (trial-3).

2. How can an app use the model?
   With the API. The app sends the customer info in JSON to /predict and gets back the answer (churn 0 or 1). I tested it in Swagger and with test_api.py. When I sent a wrong age ("abc"), the API answered 422.

3. What happens if we change the champion?
   We just move the alias to another version and restart the API. The code of the API stays the same. I tried it with move_alias.py: champion went to version 2 and then I put it back on version 1.
