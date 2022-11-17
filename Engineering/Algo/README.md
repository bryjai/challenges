# Social friend finder

Imagine that you have a list of people, where for every person you have a list of things they like (called tags), Exmaple person: John, John's tags aree: fishing, movies, etc. How would you implement an algorithm that finds matching pairs of people that like at least 2 of the same thing (have 2 tags in common).

Data model: Person(id: number, name: string, tags: list of strings)
Input: List of Persons
Output: List of pairs of Persons

### Example

Alice likes apples, movies, music, and hiking.
Bob likes football, apples, fishing and hiking.
Carol likes hiking, theater and movies.

Input:
```
[
    {
        "id": 1,
        "name": "Alice",
        "tags": ["apples", "movies", "music", "hiking"]
    },
    {
        "id": 2,
        "name": "Bob",
        "tags": ["football", "apples", "fishing", "hiking"]
    },
    {
        "id": 3,
        "name": "Carol",
        "tags": ["hiking", "theater", "movies"]
    }
]
```
Output pairs should be (Alice, Bob) and (Alice, Carol), so `[[1,2], [1,3]]`

### Answers
Please provide your answer in the form of a public github repository created by you or a gist. Make sure your name is visible and send the link to jobs@bryj.ai.
