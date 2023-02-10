# Investigating the programming abilities of ChatGPT with an abitrary DSL

## Large language models, domain-specific languages, and ChatGPT

Large language models (LLMs) such as [ChatGPT](https://openai.com/blog/chatgpt/) and [Claude](https://scale.com/blog/chatgpt-vs-claude) have demonstrated impressive programming abilities, and are capable of [solving problems](https://github.com/mccaffary/ChatGPT-Project-Euler) across a wide range of languages and their [taxonomies](https://github.com/mccaffary/ChatGPT-Domain-Specific-Language/blob/main/images/programming_language_expressiveness.png). Despite these successes, some scepticism persists over the extent to which these models exhibit any underlying appreciation of the syntactic and operational rules underlying these languages (*versus* memorisation of patterns from training data).

In this prompt-engineering repository, the programming abilities of ChatGPT are explored using an arbitrary domain-specific language (DSL). DSLs represent an attractive substrate for studying the inference capabilities of LLMs because they are novel and less likely to have been extensively encountered and memorised during training[^1]. As such, they enable a more direct test of the extent to which LLMs can infer the rules of novel programming languages in a [*few-shot manner*](https://arxiv.org/abs/2005.14165).

Here, the domain-specific language SIL (Symmetry Integration Language) was selected for two reasons. Firstly, it is extremely unlikely that ChatGPT has been exposed to any SIL code during training, as it is an in-house DSL developed by a tech-heavy hedge fund called Symmetry Investments. Secondly, as a programming language, it has some interesting features for the model to reproduce (e.g. it is a functional language, but lacks `let` expressions as in Haskell or OCaml).

[^1]: There is [evidence](https://arxiv.org/abs/2202.07646) that LLM memorisation is promoted by the frequency of training example presentation and the number of relevant tokens used to prompt the model.

## Prompt-engineering

Below is a collection of prompts consisting of short examples of SIL code which highlight its functionality. After prompting ChatGPT with the task and providing SIL code samples (see figure below; [full prompt history](https://github.com/mccaffary/ChatGPT-Domain-Specific-Language/blob/main/prompt_library/full_prompt_history.txt) and [SIL code examples](https://github.com/mccaffary/ChatGPT-Domain-Specific-Language/tree/main/images/prompts_) are also in this repo), I asked it to implement a number of standard tasks in SIL.

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
<summary>Finding similar companies</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

<details>
<summary>Finding similar companies</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

<details>
<summary>Finding similar companies</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

<details>
<summary>Finding similar companies</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

<details>
<summary>Finding similar companies</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

<details>
<summary>Finding similar companies</summary>
<br>

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
  
</details>

