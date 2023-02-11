# Investigating the programming abilities of ChatGPT with an abitrary DSL

## Large language models, domain-specific languages, and ChatGPT

Large language models (LLMs) such as [ChatGPT](https://openai.com/blog/chatgpt/) and [Claude](https://scale.com/blog/chatgpt-vs-claude) have demonstrated impressive programming abilities, and are capable of [solving problems](https://github.com/mccaffary/ChatGPT-Project-Euler) across a wide range of languages and their [taxonomies](https://github.com/mccaffary/ChatGPT-Domain-Specific-Language/blob/main/images/programming_language_expressiveness.png). Despite these successes, some scepticism persists over the extent to which these models exhibit any underlying appreciation of the syntactic and operational rules underlying these languages (*versus* memorisation of patterns from training data).

In this prompt-engineering repository, the programming abilities of ChatGPT are explored using an arbitrary domain-specific language (DSL). DSLs represent an attractive substrate for studying the inference capabilities of LLMs because they are novel and less likely to have been extensively encountered and memorised during training[^1]. As such, they enable a more direct test of the extent to which LLMs can infer the rules of novel programming languages in a [*few-shot manner*](https://arxiv.org/abs/2005.14165).

Here, the domain-specific language SIL (Symmetry Integration Language) was selected for two reasons. Firstly, it is extremely unlikely that ChatGPT has been exposed to any SIL code during training, as it is an in-house DSL developed by a tech-heavy hedge fund called Symmetry Investments. Secondly, as a programming language, it has some interesting features for the model to reproduce (e.g. it is a functional language, but lacks `let` expressions as in Haskell or OCaml).

[^1]: There is [evidence](https://arxiv.org/abs/2202.07646) that LLM memorisation is promoted by the frequency of training example presentation and the number of relevant tokens used to prompt the model.

## Prompt-engineering

Below is a collection of prompts consisting of short examples of SIL code which highlight its functionality. After prompting ChatGPT with the task and providing SIL code samples (see figure below; [full prompt history](https://github.com/mccaffary/ChatGPT-Domain-Specific-Language/blob/main/prompt_library/full_prompt_history.txt) and [SIL code examples](https://github.com/mccaffary/ChatGPT-Domain-Specific-Language/tree/main/images/prompts_) are also in this repo), I asked it to implement a number of mainstream programing tasks in SIL.

<details>
<summary>Prompt 1 (example SIL code)</summary>
<br>

- Many ways of doing this; for first product itertion, can use simply similarity metric for company information
  
- Collaborative filtering is a good first-pass for this, and an influential recent [paper](https://arxiv.org/abs/1802.05814) shows that VAEs (which I use in my modelling) outperform classic approaches at collaborative filtering (see notebook)

- Ultimately, could leverage word embeddings/ word-to-vec models, such as those used in my [research](https://snap.stanford.edu/node2vec/)
  
</details>

<details>
<summary>Prompt 2 (example SIL code)</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

<details>
<summary>Prompt 3 (example SIL code)</summary>
<br>

- Many ways of doing this; for first product itertion, can use simply similarity metric for company information
  
- Collaborative filtering is a good first-pass for this, and an influential recent [paper](https://arxiv.org/abs/1802.05814) shows that VAEs (which I use in my modelling) outperform classic approaches at collaborative filtering (see notebook)

- Ultimately, could leverage word embeddings/ word-to-vec models, such as those used in my [research](https://snap.stanford.edu/node2vec/)
  
</details>

<details>
<summary>Prompt task 1: Implement a simple relational database</summary>
<br>
  
As a first exercise, I asked the model to implement a very simple relational database in SIL, with basic functionalities such as comparing and printing the difference between two data structure (note that `//` denotes commenting in SIL).

```d
// Here, ChatGPT was prompted to write a a very simple, schematic relational database in SIL
// This prompt proved too general, perhaps, and after requesting further information, I prompted the model to generate a simple, schematic database with functionalities such as "compare" and "diff" for two or more tables

users = [    {"id": 1, "name": "John Doe", "email": "johndoe@example.com"},    {"id": 2, "name": "Jane Smith", "email": "janesmith@example.com"},    {"id": 3, "name": "Bob Johnson", "email": "bobjohnson@example.com"},]

orders = [    {"id": 1, "user_id": 1, "product": "Widget", "quantity": 2, "price": 19.99},    {"id": 2, "user_id": 2, "product": "Gadget", "quantity": 1, "price": 29.99},    {"id": 3, "user_id": 3, "product": "Thingamajig", "quantity": 3, "price": 39.99},]

// Compare two tables
compareTables(table1, table2) => {
    table1 == table2
}

//Diff two tables
diffTables(table1, table2) => {
    table1.filter(i => !table2.includes(i))
}

print(compareTables(users, users)) // true
print(diffTables(users, orders)) // [{"id": 1, "name": "John Doe", "email": "johndoe@example.com"}]
```
  
</details>

<details>
<summary>Prompt task 2: Implement bubblsort</summary>
<br>

Implementing sorting algorithms is an archetypal software engineering interview question. Here, I asked ChatGPT to implement [bubblesort](https://en.wikipedia.org/wiki/Bubble_sort) (conceptually the most basic sorting algorithm) in SIL. Below is the response:

```d
bubbleSort(arr) => {
    for i in 1...len(arr) {
        for j in 1...len(arr) - i {
            if (arr[j] > arr[j+1]) {
                temp = arr[j]
                arr[j] = arr[j+1]
                arr[j+1] = temp
            }
        }
    }
    arr
}

arr = [4, 6, 1, 3, 5, 2]
print(bubbleSort(arr))
```
Although this script is, indeed, a working implementation of bubblesort, the model broadly ignores the *functional* aspects of SIL. For instance, this implementation of bubblesort using `for` loops instead of recursion.
  
</details>

<details>
<summary>Prompt task 3: Implement a function to compute the median of an array/list</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

<details>
<summary>Prompt task 4: Implement the k-nearest neighbours algorithm</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

<details>
<summary>Prompt task 5: Solving Project Euler problems in SIL</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

