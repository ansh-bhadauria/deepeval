# Answer Relevancy

For question-answering applications, we provide a simple interface for ensuring question-answering relevancy.

:::warning

For answer-relevancy, it is important to note that it requires the answer to re-gurgitate the question. We are currently training more models to improve in answer relevancy.
If you would like beta access to our models, please feel free to reach out to jacky@twilix.io and we will get back to you soon.

:::

## Assert Answer Relevancy

```python
from deepeval.test_utils import assert_answer_relevancy
query = "What is Python?"
answer = "Python is a programming language?"
assert_answer_relevancy(query, answer, success_threshold=0.5)
```

### Parameters

- `success_threshold` refers to the minimum score for this to be considered relevant

## Answer Relevancy As A Metric

If you would instead like a score of how relevant an answer is to a query, simply call the metric class.

```python
from deepeval.metrics.answer_relevancy import AnswerRelevancy
scorer = AnswerRelevancy(success_threshold=0.5)
scorer.measure(query=query, answer=answer)
# Returns a floating point number between 0 and 1
```

### Parameters

- `success_threshold` refers to the minimum score for this to be considered relevant

## How It is Measured

Answer relevancy is measured using DL models that are trained off MS-Marco dataset (which is a search engine dataset).