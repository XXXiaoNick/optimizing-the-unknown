# optimizing-the-Unknown
**Figure 1:**
![111](./1D_optiming_processing.png)
This **Figure 1** illustrates how REBMBO's Energy-Based Model guides exploration in a 1D multi-modal function. The top panel shows the true function (black dashed line), GP model (blue line), and observations (red dots). Most importantly, it compares where UCB would sample next (purple triangles) versus where EBM-UCB samples (orange triangles). The middle panel displays the negative energy landscape, which clearly peaks at the global optimum (x≈0.25). The bottom panel shows how the EBM-UCB acquisition function (orange) differs from standard UCB (purple), directing exploration toward the global optimum rather than less promising regions.

**Addressing Reviewer Concern:** This visualization directly addresses the reviewer's statement that they "cannot see why using EBM can address the problem of excessive exploration." The figure clearly demonstrates how standard UCB would waste samples in regions far from the optimum (e.g., at x≈0.75), while EBM-UCB focuses sampling near the true optimum, guided by the energy landscape that captures global structure.

**Figure 2:**
![222](./1D_different_method.png)
This **Figure 2** shows REBMBO performance on a 1D slice of the Rosenbrock function, a challenging optimization benchmark. The top panel illustrates that the function has a narrow optimal region (true optimum marked by green line). The middle panel shows the EBM's negative energy landscape, which aligns well with valuable regions. The bottom panel compares UCB vs. EBM-UCB acquisition functions, where EBM-UCB (orange) consistently selects points closer to the optimum than standard UCB (purple).

**Addressing Reviewer Concern:** This example reinforces how REBMBO can effectively navigate difficult optimization landscapes where simple methods struggle. Rather than being "overly complex," the added complexity provides tangible benefits in directing exploration toward promising regions, addressing the reviewer's concern about whether the complexity is justified.

**Figure 3:**
![333](./2D_optimizating_processing.png)
This **Figure 2** decomposes REBMBO's key components in a 2D multi-modal setting. The top-left panel shows the true function with two distinct optima. The top-right shows GP uncertainty, while the bottom-left displays the EBM's negative energy surface. The bottom-right panel reveals the resulting EBM-UCB acquisition function with selected points from both UCB (purple dot) and EBM-UCB (orange square), where the latter is closer to a true optimum.

**Addressing Reviewer Concern:** This detailed breakdown directly addresses the reviewer's query about "why using EBM can address excessive exploration." It visually demonstrates how EBM captures global structure information and guides the acquisition function toward globally promising regions, avoiding wasteful exploration in low-value areas.

![444](./2D_Multi-modal_Optimization_Trajectory_Comparison.png)
This **Figure 4** compares optimization trajectories of GP-UCB, GLASSES, and REBMBO on a 2D multi-modal function. The top-left panel shows all three trajectories, while the remaining panels show each method individually. REBMBO (bottom-right) exhibits the most focused exploration, quickly concentrating sampling in the global optimum region. In contrast, GP-UCB and GLASSES spend more iterations in suboptimal regions.

**Addressing Reviewer Concern:** This visualization directly addresses the reviewer's request for "comparing the proposed method selection with GP-UCB/EI" and adds GLASSES comparison as requested. It clearly illustrates REBMBO's superior ability to avoid excessive exploration in areas that don't contribute to finding the global optimum.

**Figure 5:** 
![555](./GP-UCB_GLASSES_REBMBO_method.png)


**Figure 6:**
![666](./REBMBO_benefits_costs.png)
This **Figure 6** bar chart quantifies the tradeoff between performance gain and computational overhead across problems of increasing dimensionality. For each test function, it shows regret improvement percentage (blue), convergence speedup (orange), and computation overhead (green). A clear trend emerges: as problem dimensionality increases, REBMBO's benefits (blue bars) grow substantially while computational overhead (green bars) decreases relative to benefits.

**Addressing Reviewer Concern:** This directly addresses the reviewer's primary concern that "the proposed method may be over complex... [where] the gain is not clear." The visualization explicitly quantifies when the complexity is justified by showing the break-even point where benefits exceed overhead (around 5-6 dimensions).

**Figure 7:**
![777](./REBMBO_GP-UCB_comparison_table.png)
This **Figure 7** table provides a comprehensive quantitative comparison between REBMBO-C and GP-UCB across all test functions. It reports final regret values, regret improvement percentages, convergence speedup factors, computation overhead ratios, and overall efficiency scores (improvement/overhead ratio). The data clearly shows that while REBMBO performs slightly worse on the simplest problem (Sphere 2D), it delivers increasingly significant improvements as problem complexity increases.

**Addressing Reviewer Concern:** This detailed comparison directly addresses the reviewer's request for comparison with standard BO methods. The tabular format provides clear, quantifiable evidence of when REBMBO's added complexity delivers worthwhile performance improvements, directly responding to the reviewer's concern about the gain-to-complexity ratio.

**Figure 8:** 
![888](./Performance_Indicator_Heat_Map.png)
This **Figure 8** heatmap visualizes three key metrics (Regret Improvement, Convergence Speedup, and Computation Overhead) across different test functions. Color intensity indicates performance: greener cells show better improvement, while redder cells indicate worse performance. The clear color gradient demonstrates how REBMBO's benefits increase with problem dimensionality, while overhead decreases.

**Addressing Reviewer Concern:** This visualization reinforces the message that REBMBO's complexity is justified in appropriate contexts. It provides an intuitive color-based representation of the complexity-benefit tradeoff, addressing the reviewer's concern about whether the "far more complex" method delivers sufficient gains.

**Figure 9:** 
![999](./all_method_comparing.png)
This **Figure 9** dual heatmap compares all methods (GP-UCB, EI, GLASSES, REBMBO-C/S/D) across all benchmark functions on two key metrics: Final Regret (top) and Function Evaluations to reach 10% Regret (bottom). Darker blue indicates better performance. The clear color patterns show that while simpler methods are competitive on low-dimensional problems, REBMBO variants (especially REBMBO-D) dramatically outperform all baselines on higher-dimensional problems.

**Addressing Reviewer Concern:** This comprehensive comparison addresses multiple reviewer concerns: it includes all requested baseline methods (GP-UCB, EI, GLASSES), clearly shows performance on specific functions mentioned by the reviewer (Branin, Ackley, Rosenbrock), and visually demonstrates when the added complexity of REBMBO delivers substantial benefits. The dramatic improvement in evaluation efficiency (bottom panel) directly counters the suggestion that "GP-UCB and EI will perform very well" on these problems.

