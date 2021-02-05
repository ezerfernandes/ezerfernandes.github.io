---
layout: post
title: "The right reasons for using open source in research"
date: 2019-02-13
---

Paul Romer has a [blog post](https://paulromer.net/jupyter-mathematica-and-the-future-of-the-research-paper/) arguing why he thinks the future of research lies on using open source software. I think his arguments are somewhat flawed.

No offense, I am a huge fan and a huge user of open source software. I strongly support it. But I think the right arguments have to be made.

He defends that Jupyter is a better option than Mathematica mainly because the open source process behind it rewards integrity and transparency, whereas proprietary software rewards lack of integrity and secrecy. He even compares open software to the social systems that emerged from the Enlightenment and proprietary software to the horde of Vandals seeking private profit that threatened the social systems of its time. He also says Mathematica had the technical lead but was surpassed by Jupyter.

First of all, Jupyter (and the open source ecosystem behind it) has technically surpassed Mathematica because it can use free work from developers contributing to it whilst Wolfram has to pay for developers to work on Mathematica's code base. That is part of the magic of open source. But it is not because companies seek private profit. A big part of the open source development is paid by companies seekig profit. Sometimes, it is because they want to commoditize its products’ complements, as [Joel](https://www.joelonsoftware.com/2002/06/12/strategy-letter-v/) puts it. For example, a server manufacturer could pay a team to develop a open source operational system so that when someone buys a server more of the total cost from buying it goes to the company.

Second of all, it is true that an open source code base increases transparency. But there are much better reason why someone should prefer open source alternatives:

- Open standards increase user choice. If I use a proprietary format, I cannot migrate my code and my data easily to another platform. That is why I think it is better not to use AWS or Google Cloud or Azure and to use open frameworks instead when developing an app that uses the cloud, but it is another topic. It is also better using open formats such as Markdown ans LaTeX when writing  articles, notes and other textual data than relying on apps with proprietary formats.

- Another good reason to use open source software when doing research is that it increases the number of people that can run the code, because, well open source is widely available and you don't have to pay a dime for it. It is all about reproducibility and research usefulness. But it is not enough to use open source code. If you really want to increase reproducibility, you have to be careful to avoid non-deterministic elements in your code. You have to have a reproducible environment. You have to specify the version of all the libraries used. Ideally, you have to make a Docker container available so that the environment used to run the code is the same used originally and the code runs the steps in the same order.

Instead of these good reasons, Romer focuses on bashing proprietary software and exalting the open software community. He thinks Mathematica failed and Jupyter succeeded because the norms of the open source community are similar to the norms of the scientific community. I don't think it is even a reason, much less a good reason for the success of the open source software. A lot of open source developers use Apple notebooks.

I think using open source software is the best choice for research. But it is good to focus on the right reasons so you can make better choices along the way.
