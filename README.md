# Generating Figure Captions as a Text Summarization Task

We provide two suplementary data: (*i*) 200 data an (*ii*)


# Sample data 
We randomly select 200 data samples in the collected dataset that we use in the paper. 

## JSON Data Format

### JSON Scheme

- paper-title: the title of paper
- paper-abstract: the abstract of paper
- paper-url: the url link of paper
- paper-id: the unique paper ID in arXiv dataset
- figure-id: the extracted figure ID of paper (the index is not same as the label in caption)
- figure-caption: original captions of figures
- figure-caption-without-index: Removed figure index in the captions   
- paragraph: the paragraph which contain mention. Each figure may have multiple paragraphs
  - split_sentences: segmented sentences
  - mentions: mentions in the paragraph
- all-mentions: all mentions in the paper
- ocr: all texts extracted from the figure
  - extracted texts and corresponding coordinates

### Example JSON Object

An actual JSON object from dataset:

```json
{
  "paper-id": "2005.00180v1",
  "figure-id": "2005.00180v1-Figure3-1.png",
  "figure-caption": "Figure 3. Classification error rate with logistic regression under various train and test distributions",
  "figure-caption-without-index": "Classification error rate with logistic regression under various train and test distributions",
  "paragraph": [
    {
      "split_sentences": [
        "Our SE theory can also provide predictions for the correlated feature case.",
        "In this particular setting, we see that in the correlated case the test error is slightly lower in the over-parametrized regime since the energy of data is concentrated in a smaller sub-space.",
        "Interestingly, there is minimal difference between the correlated and i.i.d. cases for the under-parametrized regime when the training and test data match.",
        "When the training and test data are not matched, Logistic Regression.",
        "Fig. 3 shows a similar plot as Fig. 2 for a logistic model.",
        "Specifically, we use a logistic output P (y = 1) = 1/(1 + e \u2212p ), a binary cross entropy output loss f out (y, p), and 2 -regularization level \u03bb so that the output corresponds to the MAP estimate (we do not perform ridgeless regression in this case).",
        "The mean of the training and test eigenvalues ES 2 tr = ES 2 ts are selected such that, if the true coefficients w 0 were known, we could obtain a 5% prediction error.",
        "As in the linear case, we generate random instances of the model, use the sklearn package to perform the logistic regression, and evaluate the estimates on 1000 new test samples.",
        "We compute the median error rate (1\u2212 accuracy) and compare the simulated values with the SE theoretical estimates.",
        "The i.i.d. case was considered in (Salehi et al., 2019).",
        "Fig. 3 shows that our SE theory is able to predict the test error rate exactly in i.i.d. cases along with a correlated case and a case with training and test mismatch."
      ],
      "mentions": [
        "Fig. 3 shows a similar plot as Fig. 2 for a logistic model.",
        "Fig. 3 shows that our SE theory is able to predict the test error rate exactly in i.i.d. cases along with a correlated case and a case with training and test mismatch."
      ]
    }
  ],
  "ocr": [
    [
      [
        [
          455,
          87
        ],
        [
          579,
          87
        ],
        [
          579,
          123
        ],
        [
          455,
          123
        ]
      ],
      "i.i.d. (sim)",
      0.9129608514426719
    ],
    [
      [
        [
          38,
          108
        ],
        [
          98,
          108
        ],
        [
          98,
          138
        ],
        [
          38,
          138
        ]
      ],
      "0.40",
      0.7658763658434432
    ],
    [
      [
        [
          456,
          120
        ],
        [
          568,
          120
        ],
        [
          568,
          152
        ],
        [
          456,
          152
        ]
      ],
      "i.i.d. (SE)",
      0.7801152578973686
    ],
    [
      [
        [
          458,
          152
        ],
        [
          574,
          152
        ],
        [
          574,
          184
        ],
        [
          458,
          184
        ]
      ],
      "corr (sim)",
      0.8177585942318172
    ],
    [
      [
        [
          40,
          178
        ],
        [
          98,
          178
        ],
        [
          98,
          208
        ],
        [
          40,
          208
        ]
      ],
      "0.35",
      0.9999882578849792
    ],
    [
      [
        [
          458,
          184
        ],
        [
          564,
          184
        ],
        [
          564,
          216
        ],
        [
          458,
          216
        ]
      ],
      "corr (SE)",
      0.9997644683109389
    ],
    [
      [
        [
          457,
          213
        ],
        [
          703,
          213
        ],
        [
          703,
          249
        ],
        [
          457,
          249
        ]
      ],
      "corrtmismatch (sim)",
      0.8031683773418119
    ],
    [
      [
        [
          15,
          241
        ],
        [
          35,
          241
        ],
        [
          35,
          303
        ],
        [
          15,
          303
        ]
      ],
      "8",
      0.8052469947599548
    ],
    [
      [
        [
          457,
          245
        ],
        [
          693,
          245
        ],
        [
          693,
          281
        ],
        [
          457,
          281
        ]
      ],
      "corr+mismatch (SE)",
      0.771997295070924
    ],
    [
      [
        [
          40,
          248
        ],
        [
          98,
          248
        ],
        [
          98,
          278
        ],
        [
          40,
          278
        ]
      ],
      "0.30",
      0.9999615550041199
    ],
    [
      [
        [
          10,
          300
        ],
        [
          38,
          300
        ],
        [
          38,
          360
        ],
        [
          10,
          360
        ]
      ],
      "2",
      0.519363508807146
    ],
    [
      [
        [
          38,
          318
        ],
        [
          96,
          318
        ],
        [
          96,
          348
        ],
        [
          38,
          348
        ]
      ],
      "0.25",
      0.9998639225959778
    ],
    [
      [
        [
          38,
          388
        ],
        [
          96,
          388
        ],
        [
          96,
          416
        ],
        [
          38,
          416
        ]
      ],
      "0.20",
      0.9795447126002993
    ],
    [
      [
        [
          38,
          458
        ],
        [
          94,
          458
        ],
        [
          94,
          486
        ],
        [
          38,
          486
        ]
      ],
      "0.15",
      0.782281300716131
    ],
    [
      [
        [
          90,
          526
        ],
        [
          134,
          526
        ],
        [
          134,
          556
        ],
        [
          90,
          556
        ]
      ],
      "0.0",
      0.9999533364464172
    ],
    [
      [
        [
          186,
          526
        ],
        [
          228,
          526
        ],
        [
          228,
          554
        ],
        [
          186,
          554
        ]
      ],
      "0.5",
      0.9999823118634976
    ],
    [
      [
        [
          380,
          526
        ],
        [
          422,
          526
        ],
        [
          422,
          556
        ],
        [
          380,
          556
        ]
      ],
      "1.5",
      0.9999079808531304
    ],
    [
      [
        [
          282,
          528
        ],
        [
          326,
          528
        ],
        [
          326,
          556
        ],
        [
          282,
          556
        ]
      ],
      "1.0",
      0.9998061210412578
    ],
    [
      [
        [
          476,
          528
        ],
        [
          518,
          528
        ],
        [
          518,
          556
        ],
        [
          476,
          556
        ]
      ],
      "2.0",
      0.9975951313972473
    ],
    [
      [
        [
          572,
          528
        ],
        [
          612,
          528
        ],
        [
          612,
          554
        ],
        [
          572,
          554
        ]
      ],
      "2.5",
      0.9472689628601074
    ],
    [
      [
        [
          668,
          528
        ],
        [
          710,
          528
        ],
        [
          710,
          554
        ],
        [
          668,
          554
        ]
      ],
      "3.0",
      0.4177738230741822
    ],
    [
      [
        [
          464.1758366163079,
          548.1154281570775
        ],
        [
          511.7775429310856,
          556.8663090077201
        ],
        [
          504.8241633836921,
          588.8845718429225
        ],
        [
          457.2224570689144,
          579.1336909922799
        ]
      ],
      "Nlp",
      0.9622125904428532
    ],
    [
      [
        [
          310,
          550
        ],
        [
          463,
          550
        ],
        [
          463,
          588
        ],
        [
          310,
          588
        ]
      ],
      "Sample ratio",
      0.9674623074933132
    ]
  ],
  "paper-title": "Generalization Error of Generalized Linear Models in High Dimensions",
  "paper-abstract": "At the heart of machine learning lies the question of generalizability of learned rules over previously unseen data. While over-parameterized models based on neural networks are now ubiquitous in machine learning applications, our understanding of their generalization capabilities is incomplete. This task is made harder by the non-convexity of the underlying learning problems. We provide a general framework to characterize the asymptotic generalization error for single-layer neural networks (i.e., generalized linear models) with arbitrary non-linearities, making it applicable to regression as well as classification problems. This framework enables analyzing the effect of (i) over-parameterization and non-linearity during modeling; and (ii) choices of loss function, initialization, and regularizer during learning. Our model also captures mismatch between training and test distributions. As examples, we analyze a few special cases, namely linear regression and logistic regression. We are also able to rigorously and analytically explain the \\emph{double descent} phenomenon in generalized linear models.",
  "paper-url": "https://arxiv.org/pdf/2005.00180v1.pdf",
  "all-mentions": [
    [
      "Fig. 3 shows a similar plot as Fig. 2 for a logistic model.",
      "Fig. 3 shows that our SE theory is able to predict the test error rate exactly in i.i.d. cases along with a correlated case and a case with training and test mismatch."
    ]
  ]
},
```
