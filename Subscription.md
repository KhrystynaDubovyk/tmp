# SDL Subscription states

## SubscribeVehicleData

Not subscribed ---> Subscribed

| | Use case 1 | Use case 2 | Use case 3 |
|---|---|---|---|
**Start state** | Not subscribed | Subscribed (param1) | Subscribed (param1) |
**Input** | SubscribeVehicleData (param1) | SubscribeVehicleData (param1) | SubscribeVehicleData (param2) |
**Finish state** | Subscribed (param1) | Subscribed (param1) | Subscribed (param1, param2) | 

## UnsubscribeVehicleData

Subscribed ---> Not subscribed 

| | Use case 1 | Use case 2 | Use case 3 |
|---|---|---|---|
**Start state** | Subscribed (param1) | Not subscribed | Subscribed (param1, param2) |
**Input** | UnsubscribeVehicleData (param1) | UnsubscribeVehicleData (param1) | UnsubscribeVehicleData (param1) |
**Finish state** | Not subscribed | Not subscribed | Subscribed (param2) | 
