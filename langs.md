# 📚 Exemplos de Lista Encadeada por Linguagem

Este documento apresenta exemplos didáticos de implementação de **lista encadeada simples** em diferentes linguagens.

Cada exemplo inclui:

* Estrutura de nó
* Inserção no final
* Impressão da lista

---

# 1) Elixir

```elixir
defmodule Node do
  defstruct value: nil, next: nil
end

defmodule LinkedList do
  def new do
    nil
  end

  def append(nil, value) do
    %Node{value: value, next: nil}
  end

  def append(%Node{value: v, next: next}, value) do
    %Node{value: v, next: append(next, value)}
  end

  def print(nil) do
    IO.puts("fim")
  end

  def print(%Node{value: value, next: next}) do
    IO.write("#{value} -> ")
    print(next)
  end
end
```

---

# 2) Rust

```rust
#[derive(Debug)]
struct Node {
    value: String,
    next: Option<Box<Node>>,
}

struct LinkedList {
    head: Option<Box<Node>>,
}
```

---

# 3) Crystal

```crystal
class Node
  property value : String
  property next_node : Node?

  def initialize(@value : String)
    @next_node = nil
  end
end
```

---

# 4) Java

```java
class Node {
    String value;
    Node next;

    Node(String value) {
        this.value = value;
        this.next = null;
    }
}
```

---

# 5) Nim

```nim
type
  Node = ref object
    value: string
    next: Node
```

---

# 6) Julia

```julia
mutable struct Node
    value::String
    next::Union{Nothing, Node}
end
```

---

# 7) Lean

```lean
inductive LinkedList where
  | nil : LinkedList
  | node : String → LinkedList → LinkedList
```

---

# 📌 Observação

Cada linguagem implementa o conceito de lista encadeada de acordo com seu paradigma:

* Imperativas/OOP → nós + referências
* Funcionais → estruturas recursivas

O importante é entender o conceito de encadeamento entre elementos.

