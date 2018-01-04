# SubscribeVehicleData/UnsubscribeVehicleData states

## SubscribeVehicleData

Not subscribed ---> Subscribed

| | Use case 1 | Use case 2 | Use case 3 |
|---|---|---|---|
**Start state** | Not subscribed | Subscribed (P1) | Subscribed (P1) |
**Input** | SubscribeVehicleData (P1) | SubscribeVehicleData (P1) | SubscribeVehicleData (P2) |
**Finish state** | Subscribed (P1) | Subscribed (P1) | Subscribed (P1, P2) | 

## UnsubscribeVehicleData

Subscribed ---> Not subscribed 

| | Use case 1 | Use case 2 | Use case 3 |
|---|---|---|---|
**Start state** | Subscribed (P1) | Not subscribed | Subscribed (P1, P2) |
**Input** | UnsubscribeVehicleData (P1) | UnsubscribeVehicleData (P1) | UnsubscribeVehicleData (P1) |
**Finish state** | Not subscribed | Not subscribed | Subscribed (P2) | 
