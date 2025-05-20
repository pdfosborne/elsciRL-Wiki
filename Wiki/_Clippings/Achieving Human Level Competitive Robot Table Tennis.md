---
cite: "tabletennis2024"
title: "Achieving Human Level Competitive Robot Table Tennis"
url: "https://arxiv.org/abs/2408.03906"
authors:
  - "D'Ambrosio"
  - "David B."
  - "Abeyruwan"
  - "Saminda"
  - "Graesser"
  - "Laura"
  - "Iscen"
  - "Atil"
  - "Amor"
  - "Heni Ben"
  - "Bewley"
  - "Alex"
  - "Reed"
  - "Barney J."
  - "Reymann"
  - "Krista"
  - "Takayama"
  - "Leila"
  - "Tassa"
  - "Yuval"
  - "Choromanski"
  - "Krzysztof"
  - "Coumans"
  - "Erwin"
  - "Jain"
  - "Deepali"
  - "Jaitly"
  - "Navdeep"
  - "Jaques"
  - "Natasha"
  - "Kataoka"
  - "Satoshi"
  - "Kuang"
  - "Yuheng"
  - "Lazic"
  - "Nevena"
  - "Mahjourian"
  - "Reza"
  - "Moore"
  - "Sherry"
  - "Oslund"
  - "Kenneth"
  - "Shankar"
  - "Anish"
  - "Sindhwani"
  - "Vikas"
  - "Vanhoucke"
  - "Vincent"
  - "Vesom"
  - "Grace"
  - "Xu"
  - "Peng"
  - "Sanketi"
  - "Pannag R."
publisher: "arxiv"
site: "arxiv"
published: 07/08/2024
year: 2024
created: 2025-05-04
description: "Robot achieves amateur human-level table tennis via hierarchical policy and sim-to-real techniques."
tags:
  - "robotics"
  - "tabletennis"
  - "sim-to-real"
  - "hierarchicalpolicy"
  - "AI"
type: "ArXiv"
BibTeX (AI Generated): "@article{tabletennis2024,  author = {D'Ambrosio, David B. and Abeyruwan, Saminda and Graesser, Laura and Iscen, Atil and Amor, Heni Ben and Bewley, Alex and Reed, Barney J. and Reymann, Krista and Takayama, Leila and Tassa, Yuval and Choromanski, Krzysztof and Coumans, Erwin and Jain, Deepali and Jaitly, Navdeep and Jaques, Natasha and Kataoka, Satoshi and Kuang, Yuheng and Lazic, Nevena and Mahjourian, Reza and Moore, Sherry and Oslund, Kenneth and Shankar, Anish and Sindhwani, Vikas and Vanhoucke, Vincent and Vesom, Grace and Xu, Peng and Sanketi, Pannag R.},  title = {Achieving Human Level Competitive Robot Table Tennis},  year = {2024},  publisher = {arXiv}}"
citations: 0
---
# Summary

A robot agent achieves amateur human-level performance in competitive table tennis using a hierarchical policy architecture, zero-shot sim-to-real techniques, and real-time adaptation to unseen opponents. The robot won 45% of matches against humans of varying skill levels.

----
# Article

Achieving Human Level Competitive Robot Table Tennis

Achieving human-level speed and performance on real-world tasks is a north star for the robotics research community. This work takes a step towards that goal and presents the first learned robot agent that reaches amateur human-level performance in competitive table tennis.

Table tennis is a physically demanding sport which requires human players to undergo years of training to achieve an advanced level of proficiency. In this paper, we contribute:

1.  A hierarchical and modular policy architecture consisting of:
    *   Low-level controllers with their detailed skill descriptors which model the agent's capabilities and help to bridge the sim-to-real gap.
    *   A high-level controller that chooses the low-level skills.
2.  Techniques for enabling zero-shot sim-to-real including an iterative approach to defining the task distribution that is grounded in the real-world and defines an automatic curriculum.
3.  Real time adaptation to unseen opponents.

Policy performance was assessed through 29 robot vs. human matches of which the robot won 45% (13/29). All humans were unseen players and their skill level varied from beginner to tournament level. Whilst the robot lost all matches vs. the most advanced players it won 100% matches vs. beginners and 55% matches vs. intermediate players, demonstrating solidly amateur human-level performance.

Videos of the matches can be viewed at https://sites.google.com/view/competitive-robot-table-tennis
