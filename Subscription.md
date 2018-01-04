# SDL Subscription states

Affected RPCs: SubscribeVehicleData, SubscribeWayPoints

## Subscribe

Not subscribed ---> Subscribed

| | Use case 1 | Use case 2 | Use case 3 |
|---|---|---|---|
**Start state** | Not subscribed | Subscribed (P1) | Subscribed (P1) |
**Input** | To subscribe (P1) | To subscribe (P1) | To subscribe (P2) |
**Finish state** | Subscribed (P1) | Subscribed (P1) | Subscribed (P1, P2) | 

## Unsubscribe

Subscribed ---> Not subscribed 

| | Use case 1 | Use case 2 | Use case 3 |
|---|---|---|---|
**Start state** | Subscribed (P1) | Not subscribed | Subscribed (P1, P2) |
**Input** | To unsubscribe (P1) | To unsubscribe (P1) | To unsubscribe (P1) |
**Finish state** | Not subscribed | Not subscribed | Subscribed (P2) | 
