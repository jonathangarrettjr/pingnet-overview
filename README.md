# PingNet

PingNet’s working Python prototype relays authenticated work-zone messages locally among equipped, participating nodes without requiring continuous cellular or cloud connectivity. The tabletop tests measured message delivery between nodes. They did not establish automatic failover between PingNet and existing communications systems.

**[Walk us through one work-zone update.](https://pingnet.net/#contact)** If a lane reopens early, how does the crew report it, who verifies the change, and when does the new status appear in the public feed?

## How local relay works

A participating node signs a work-zone message. Receiving nodes check the signature against the configured trust rules, check for replays or duplicates, and relay eligible messages. Observers record receipts for analysis after the run.

A valid signature ties the message to a trusted signing key. A person still has to establish whether the lane is open. The prototype carries a reported condition.

## Tabletop evidence

**Six-node demonstration.** The video shows the prototype on a tabletop with equipment representing the work zone, vehicles, infrastructure, a responder, and an observer. [Watch the six-node video.](https://pingnet.net/#demo)

**Three ten-node runs.** On June 7, 2026, all ten expected nodes appeared in each of three separate tabletop runs. Each run called for 18 downstream receipts. A receipt records that an expected node processed a message.

| Run | Receipts | Node latency (p95) |
| --- | ---: | ---: |
| First | 18 of 18 | 43 ms |
| Second | 18 of 18 | 33 ms |
| Third | 18 of 18 | 30 ms |

<details>
<summary>June 7 run IDs in table order</summary>

1. `run-10node-20260607-190405` (43 ms)
2. `run-10node-20260607-192316` (33 ms)
3. `run-10node-20260607-193016` (30 ms)

</details>

Across the three runs, the nodes recorded **54 of 54 expected downstream receipts**. For each run, the p95 is the 95th percentile of the time from message creation to processing at a receiving node. The tests used scripted work-zone events on a tabletop. Crew reporting time, operator verification, public-feed timing, public-road performance, and safety outcomes remain unmeasured. [See the test record.](https://pingnet.net/#evidence)

### Post-run exports

After a run, PingNet can produce CWZ/WZDx-style GeoJSON files for review. The work-zone example uses modeled geometry and a scenario lane status. Its timestamps come from test records. These files demonstrate an export format. A live agency connection and formal standards conformance would each require separate verification.

## One lane reopening

Consider an illustrative workflow. A crew reports an early reopening through its usual channel. Operations checks the report against the agency’s evidence requirements. The agency decides whether to publish a change to its feed and retains publishing authority.

We want to understand where the wait happens. A local relay could help if a report struggles to reach operations. If the wait comes after verification, a faster relay may make little difference. We have yet to measure that workflow with an operator.

## A possible feasibility evaluation

If an operator identifies a specific delay and wants to investigate it, we can scope a potentially paid evaluation together. One option is to compare the operator’s usual process with the same process supplemented by a PingNet message. A staged reopening and an isolated copy of the feed would let the team time the report, verification, and public-facing update against an independent record of the physical change.

The operator and PingNet would agree on the question, permissions, cost, and what result would justify further work. A separate technical review could be included in that scope.

Work zones are our first use case. [See where PingNet is headed.](https://pingnet.net/#direction)

## Contact

Jonathan Garrett Jr., founder of PingNet LLC. [Email Jonathan](mailto:jonathan.garrettjr@pingnet.net), [call +1 (202) 656-5639](tel:+12026565639), or [find a time to talk](https://calendly.com/jonathan-garrettjr-pingnet).

[PingNet website](https://pingnet.net/) · [Founder’s GitHub profile](https://github.com/jonathangarrettjr) · [LinkedIn](https://www.linkedin.com/in/jonathan-garrett-jr/)
