---
cite: "ELF24"
title: "ELF-Gym: Evaluating Large Language Models Generated Features for Tabular Prediction | Proceedings of the 33rd ACM International Conference on Information and Knowledge Management"
url: "https://dl.acm.org/doi/10.1145/3627673.3679153"
authors:
  - "Edoardo Serra"
  - "Francesca Spezzano"
publisher: "dl.acm"
site: "dl.acm"
published: 21/10/2024
year: 2024
created: 2025-06-11
description: "ELF-Gym evaluates LLM-generated features for tabular prediction using Kaggle data."
tags:
  - "datascience"
  - "featureengineering"
  - "largelanguagemodels"
type: "Conference Paper"
BibTeX (AI Generated): "@inproceedings{ELF24, author = {Edoardo Serra and Francesca Spezzano}, title = {ELF-Gym: Evaluating Large Language Models Generated Features for Tabular Prediction}, booktitle = {CIKM '24: Proceedings of the 33rd ACM International Conference on Information and Knowledge Management}, year = {2024}, publisher = {ACM}, doi = {10.1145/3627673.3679153}}"
citations: 0
---
# Summary

ELF-Gym evaluates LLM-generated features for tabular prediction using a new dataset from Kaggle competitions. It measures the impact on model performance and alignment with expert features.

----
# Article

# ELF-Gym: Evaluating Large Language Models Generated Features for Tabular Prediction | Proceedings of the 33rd ACM International Conference on Information and Knowledge Management

Crafting effective features is a crucial yet labor-intensive and domain-specific task within machine learning pipelines. Fortunately, recent advancements in Large Language Models (LLMs) have shown promise in automating various data science tasks, including feature engineering. But despite this potential, evaluations thus far are primarily based on the end performance of a complete ML pipeline, providing limited insight into precisely how LLMs behave relative to human experts in feature engineering. To address this gap, we propose ELF-Gym, a framework for Evaluating LLM-generated Features. We curated a new dataset from historical Kaggle competitions, including 251 golden features used by top-performing teams. ELF-Gym then quantitatively evaluates LLM-generated features by measuring their impact on downstream model performance as well as their alignment with expert-crafted features through semantic and functional similarity assessments. This approach provides a more comprehensive evaluation of disparities between LLMs and human experts, while offering valuable insights into specific areas where LLMs may have room for improvement. For example, using ELF-Gym we empirically demonstrate that, in the best-case scenario, LLMs can semantically capture approximately 56% of the golden features, but at the more demanding implementation level this overlap drops to 13%. Moreover, in other cases LLMs may fail completely, particularly on datasets that require complex features, indicating broad potential pathways for improvement.

## References

[1] Josh Achiam, Steven Adler, Sandhini Agarwal, Lama Ahmad, Ilge Akkaya, Florencia Leoni Aleman, Diogo Almeida, Janko Altenschmidt, Sam Altman, Shyamal Anadkat, et al. 2023. Gpt-4 technical report. arXiv preprint arXiv:2303.08774 (2023).

[2] AI@Meta. 2024. Llama 3 Model Card. (2024). https://github.com/meta-llama/llama3/blob/main/MODEL_CARD.md

[3] alokgupta, Anna Montoya, LizSellier, Meghan O'Connell, and Wendy Kan. 2015. Airbnb New User Bookings. https://kaggle.com/competitions/airbnb-recruiting-new-user-bookings

[4] AI Anthropic. 2024. The claude 3 model family: Opus, sonnet, haiku. Claude-3 Model Card (2024).

[5] Jacob Austin, Augustus Odena, Maxwell Nye, Maarten Bosma, Henryk Michalewski, David Dohan, Ellen Jiang, Carrie Cai, Michael Terry, Quoc Le, et al. 2021. Program synthesis with large language models. arXiv preprint arXiv:2108.07732 (2021).

[6] Lochan Basyal and Mihir Sanghvi. 2023. Text Summarization Using Large Language Models: A Comparative Study of MPT-7b-instruct, Falcon-7b-instruct, and OpenAI Chat-GPT Models. arXiv preprint arXiv:2310.10449 (2023).

[7] Mark Chen, Jerry Tworek, Heewoo Jun, Qiming Yuan, Henrique Ponde de Oliveira Pinto, Jared Kaplan, Harri Edwards, Yuri Burda, Nicholas Joseph, Greg Brockman, et al. 2021. Evaluating large language models trained on code. arXiv preprint arXiv:2107.03374 (2021).

[8] Tianqi Chen and Carlos Guestrin. 2016. Xgboost: A scalable tree boosting system. In Proceedings of the 22nd acm sigkdd international conference on knowledge discovery and data mining. 785--794.

[9] DannyBickson, Freedom, Guy Rapaport, HanZhu, Ibrahim, RossWang, Wendy Kan, Yangyang, and Yao Lu. 2016. TalkingData Mobile User Demographics. https://kaggle.com/competitions/talkingdata-mobile-user-demographics

[10] Mengnan Du, Fengxiang He, Na Zou, Dacheng Tao, and Xia Hu. 2023. Shortcut learning of large language models in natural language understanding. Commun. ACM, Vol. 67, 1 (2023), 110--120.

[11] Jim Dullaghan, John P. Costella, John_W, Meghan O'Connell, Rafael, Ruchi, Ruchi Varshney, Sergey, Sofus Macskassy, and Wendy Kan. 2015. Facebook Recruiting IV: Human or Robot? https://kaggle.com/competitions/facebook-recruiting-iv-human-or-bot

[12] Nick Erickson, Jonas Mueller, Alexander Shirkov, Hang Zhang, Pedro Larroy, Mu Li, and Alexander Smola. 2020. AutoGluon-Tabular: Robust and Accurate AutoML for Structured Data. arXiv preprint arXiv:2003.06505 (2020).

[13] Tanya Goyal, Junyi Jessy Li, and Greg Durrett. 2022. News summarization and evaluation in the era of gpt-3. arXiv preprint arXiv:2209.12356 (2022).

[14] Siyuan Guo, Cheng Deng, Ying Wen, Hechang Chen, Yi Chang, and Jun Wang. 2024. DS-Agent: Automated Data Science by Empowering Large Language Models with Case-Based Reasoning. arXiv preprint arXiv:2402.17453 (2024).

[15] Ivan Guz, night_bat, and Wendy Kan. 2015. Avito Context Ad Clicks. https://kaggle.com/competitions/avito-context-ad-clicks

[16] Sungwon Han, Jinsung Yoon, Sercan O Arik, and Tomas Pfister. 2024. Large Language Models Can Automatically Engineer Features for Few-Shot Tabular Learning. arXiv preprint arXiv:2404.09491 (2024).

[17] Noah Hollmann, Samuel Müller, and Frank Hutter. 2024. Large language models for automated data science: Introducing caafe for context-aware automated feature engineering. Advances in Neural Information Processing Systems, Vol. 36 (2024).

[18] Franziska Horn, Robert Pack, and Michael Rieger. 2020. The autofeat python library for automated feature engineering and selection. In Machine Learning and Knowledge Discovery in Databases: International Workshops of ECML PKDD 2019, Würzburg, Germany, September 16--20, 2019, Proceedings, Part I. Springer, 111--120.

[19] Addison Howard, Bernadette Bouchon-Meunier, IEEE CIS, inversion, John Lei, Lynn@Vesta, Marcus2010, and Prof. Hussein Abbass. 2019. IEEE-CIS Fraud Detection. https://kaggle.com/competitions/ieee-fraud-detection

[20] sharathrao Will Cukierski jeremy stanley, Meg Risdal. 2017. Instacart Market Basket Analysis. https://kaggle.com/competitions/instacart-market-basket-analysis

[21] Albert Q Jiang, Alexandre Sablayrolles, Antoine Roux, Arthur Mensch, Blanche Savary, Chris Bamford, Devendra Singh Chaplot, Diego de las Casas, Emma Bou Hanna, Florian Bressand, et al. 2024. Mixtral of experts. arXiv preprint arXiv:2401.04088 (2024).

[22] Yuchin Juan, Yong Zhuang, Wei-Sheng Chin, and Chih-Jen Lin. 2016. Field-aware factorization machines for CTR prediction. In Proceedings of the 10th ACM conference on recommender systems. 43--50.

[23] Kaggle. [n.,d.]. Kaggle. https://www.kaggle.com

[24] Wendy Kan. 2015. West Nile Virus Prediction. https://kaggle.com/competitions/predict-west-nile-virus

[25] James Max Kanter and Kalyan Veeramachaneni. 2015. Deep feature synthesis: Towards automating data science endeavors. In 2015 IEEE international conference on data science and advanced analytics (DSAA). IEEE, 1--10.

[26] Guolin Ke, Qi Meng, Thomas Finley, Taifeng Wang, Wei Chen, Weidong Ma, Qiwei Ye, and Tie-Yan Liu. 2017. Lightgbm: A highly efficient gradient boosting decision tree. Advances in neural information processing systems, Vol. 30 (2017).

[27] Albert Lu, Hongxin Zhang, Yanzhe Zhang, Xuezhi Wang, and Diyi Yang. 2023. Bounding the capabilities of large language models in open text generation with prompt constraints. arXiv preprint arXiv:2302.09185 (2023).

[28] Bonan Min, Hayley Ross, Elior Sulem, Amir Pouran Ben Veyseh, Thien Huu Nguyen, Oscar Sainz, Eneko Agirre, Ilana Heintz, and Dan Roth. 2023. Recent advances in natural language processing via large pre-trained language models: A survey. Comput. Surveys, Vol. 56, 2 (2023), 1--40.

[29] mjkistler, Ran Locar, Ronny Lempel, RoySassonOB, Rwagner, and Will Cukierski. 2016. Outbrain Click Prediction. https://kaggle.com/competitions/outbrain-click-prediction

[30] The pandas development team. 2020. pandas-dev/pandas: Pandas. https://doi.org/10.5281/zenodo.3509134

[31] Steffen Rendle. 2010. Factorization machines. In 2010 IEEE International conference on data mining. IEEE, 995--1000.

[32] Qitao Shi, Ya-Lin Zhang, Longfei Li, Xinxing Yang, Meng Li, and Jun Zhou. 2020. Safe: Scalable automatic feature engineering framework for industrial tasks. In 2020 IEEE 36th International Conference on Data Engineering (ICDE). IEEE, 1645--1656.

[33] Ann Yuan, Andy Coenen, Emily Reif, and Daphne Ippolito. 2022. Wordcraft: story writing with large language models. In 27th International Conference on Intelligent User Interfaces. 841--852.

[34] Shun Zhang, Zhenfang Chen, Yikang Shen, Mingyu Ding, Joshua B Tenenbaum, and Chuang Gan. 2023. Planning with large language models for code generation. arXiv preprint arXiv:2303.05510 (2023).

[35] Tianyi Zhang, Faisal Ladhak, Esin Durmus, Percy Liang, Kathleen McKeown, and Tatsunori B Hashimoto. 2024. Benchmarking large language models for news summarization. Transactions of the Association for Computational Linguistics, Vol. 12 (2024), 39--57.

[36] Tianping Zhang, Zheyu Zhang, Haoyan Luo, Fengyuan Liu, Wei Cao, and Jian Li. 2022. Openfe: Automated feature generation beyond expert-level performance. (2022).

