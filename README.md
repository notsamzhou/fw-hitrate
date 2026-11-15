# fw-hitrate

An analysis of the hit rate in **Fortune's Weave**: does the displayed hit chance match how often attacks actually land, and which random-number system does the game use?
[fw-hitrate.ipynb](fw-hitrate.ipynb) compares three candidate systems across every displayed hit rate (0–100%):

- **One RN** – one roll 0–99; hits if below the displayed rate.
- **True hit (2 RN)** – two rolls averaged; hits if below the displayed rate.
- **Hybrid** – one RN below 50%, then an adjusted formula above 50%.

It then tests each system against 150 recorded attacks at two displayed rates, using a bootstrap 95% confidence interval.

## Results

At 24%, true hit is ruled out (p ≈ 9e-6). At 78%, one RN is ruled out. Hybrid is the only system consistent with both experiments.

## Run it

```bash
uv sync
```

Then open `fw-hitrate.ipynb` in VS Code or Jupyter and run all cells.
