KSC2025


# 멀티티어 액터 프로그래밍 언어의 설계 및 구현


### 예제 프로그램

- 분산된 위치의 S K 조합자
  - [RPC 계산법](https://github.com/chaendaya/ksc2025/blob/587414201f8991c829eb118d5d5391119a0e06da/multitier_actor/app/actors/examples/ksc2025/skki.actor)

  - [순수 액터 기반](https://github.com/chaendaya/ksc2025/blob/587414201f8991c829eb118d5d5391119a0e06da/multitier_actor/app/actors/examples/ksc2025/skki_actor.actor) 

- 멀티티어 벤치마크
  - [Chat](https://github.com/chaendaya/ksc2025/blob/587414201f8991c829eb118d5d5391119a0e06da/multitier_actor/app/actors/examples/ksc2025/chat_dynamic.actor)

  - [TokenRing](https://github.com/chaendaya/ksc2025/blob/587414201f8991c829eb118d5d5391119a0e06da/multitier_actor/app/actors/examples/ksc2025/tokenring.actor)

  - [MasterWorker](https://github.com/chaendaya/ksc2025/blob/587414201f8991c829eb118d5d5391119a0e06da/multitier_actor/app/actors/examples/ksc2025/masterworker.actor)

  - [HO-Book-Seller](https://github.com/chaendaya/ksc2025/blob/587414201f8991c829eb118d5d5391119a0e06da/multitier_actor/app/actors/examples/ksc2025/booksellerHO.actor)



------

## Implementation
Built on pure functional Haskell, MAPL integrates RPC calculus into Agha’s Actor model
and supporting real distributed execution on Cloud Haskell.

<img width="782" height="292" alt="image" src="https://github.com/user-attachments/assets/94782368-bb28-435a-aee8-f4d68a25344c" />

- multi-tier actor calculus (operational semantics) (2025.09 update)
  [mapl_semantics.pdf](https://github.com/user-attachments/files/22930462/mapl_semantics.pdf)





## Build and Run Instructions

```
> cd splashsrc2025\multitier_actor

> stack build multitier-actor:exe:actors-exe

> stack run actors-exe main <ip>:<port> .\app\actors\examples\splashsrc2025\<fileName>
```
e.g. 
`stack run actors-exe main 127.0.0.1:8080 .\app\actors\examples\splashsrc2025\bookseller1.actor`




When you want dynamic attatchment (e.g. chat program)

```
> stack run actors-exe main <main-ip>:<main-port> .\app\actors\examples\splashsrc2025\chat_dynamic.actor

> stack run actors-exe client <cli1-ip>:<cli1-port> <main-ip>:<main-port> .\app\actors\examples\splashsrc2025\chat_dynamic.actor

> stack run actors-exe client <cli2-ip>:<cli2-port> <main-ip>:<main-port> .\app\actors\examples\splashsrc2025\chat_dynamic.actor

...
```
