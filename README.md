# Azure Landing Zones Library Concept

This repo is designed to show how a reference Azure Landing Zones architecture can be represented in a semi-structured data model in a repository.

## Data model visualisation

```text
                     ┌─────────────────────────┐
                     │                         │
                  ┌──┤ Resource deployments    │
                  │  │                         │
                  │  └──────────────────────┬──┘
                  │                         │
                  └──────────────┬──────────┘
                                 │
                                 │
                                 │
                                 │
                                 │
                  ┌──────────────▼──────────────┐
                  │                             │
                  │  Resource deployment to     │
                  │  subscription alias mapping │
                  │                             │
                  └──────────────┬──────────────┘
                                 │
                                 │
                                 │
                                 ▼
                     ┌─────────────────────────┐
                     │                         │
                  ┌──┤  Subscription aliases   │
                  │  │                         │
                  │  └──────────────────────┬──┘
                  │                         │
                  └──────────────┬──────────┘
                                 │
                                 │
                                 │
                                 │
                                 │
                                 ▼
               ┌────────────────────────────────┐
               │                                │
               │  Subscription to management    │
               │  group mapping                 │
               │                                │
               └────────────────────────────────┘
                                 ▲
                                 │
                                 │
                                 │
                                 │
                                 │
                     ┌───────────┴─────────┐
                     │                     │
                  ┌──┤ Management groups   │
                  │  │                     │
                  │  └──────────────────┬──┘
                  │                     │
                  └────────────┬────────┘
                               │
                               │
                               │
                               ▼
                   ┌──────────────────────┐
                   │                      │
                   │ Management group to  │
                   │ archetype mapping    │
                   │                      │
                   └──────────────────────┘
                               ▲
                               │
                               │
                               │
                   ┌───────────┴──────────┐
                   │                      │
                   │                      │
┌──────────────┬──►│ Archetype definition │◄───────┬───────────┐
│              │   │                      │        │           │
│              │   │                      │        │           │
│              │   └──────────────────────┘        │           │
│              │                                   │           │
│              │                                   │           │
│              │                                   │           │
│  ┌───────────┴──────────┐        ┌───────────────┴────────┐  │
│  │                      │        │                        │  │
│  │  Role definitions    │        │  Role assignments      │  │
│  │                      │        │                        │  │
│  └──────────────────────┘        └────────────────────────┘  │
│                                                              │
│  ┌──────────────────────┐        ┌────────────────────────┐  │
│  │                      │        │                        │  │
├──┤  Policy definitions  │        │  Policy assignments    ├──┘
│  │                      │        │                        │
│  └──────────────────────┘        └────────────────────────┘
│
│  ┌────────────────────────┐
│  │                        │
└──┤ Policy set definitions │
   │                        │
   └────────────────────────┘
```
