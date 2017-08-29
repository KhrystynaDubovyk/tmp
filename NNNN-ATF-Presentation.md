# Automated Test Framework

## Basics
ATF is a main tool for automated black-box testing of SDL.
It consists of a set of Lua classes and extensions and provide a simple way to create, manage and use network connections, process Mobile and HMI APIs protocol messages. That is everything required for communication with SDL. Test consists of several use cases — a set of data to be sent to input SDL channels and data expected to be received from SDL output.

## Structure
_diagram_

## Main parts

### Configuration
Main configuration file is `./modules/config.lua`
In most of the case default values have to be used

### Runner
Runner is a simple bash script. It allows to run single test script. Usage:
```
./start.sh [options] [script file name]
```
One of the option can be path to SDL binaries. Example:
```
./start.sh --sdl-core=/home/user/development/sdl/build/bin ./test_scripts/ActivationDuringActiveState.lua
```

### Connectivity test
A connectivity test module `./modules/connecttest.lua` provides the following:
 - connection to Mobile and HMI SDL channels 
 - a set of methods to send reqests/notifications and to register expectations on these channels
 - methods to start and stop services
 - methods to start and stop streaming

### Test Script
Test script is just a Lua program. Usualy it consists of a set of Test Steps. 
Each test step is a sequence of requests/notifications and expectations. 
When SDL responds, expectations are verified, and if all expectations have been satisfied, the test case is considered passed.

## Requests
ATF allows to send requests and notifications on a both available SDL channels - Mobile and HMI

### Mobile side
- SendRPC
- Send

### HMI side
HMI connection provides following functions
- SendRequest
- SendNotification
- SendResponse
- Send

## Expectations
To specify what data is expected to be received from SDL, the Expectations Table is used. Every item of this table describes single message. To simplify Expectations writing ATF provides several functions making typical expectations.

### Mobile side
- EXPECT_RESPONSE
- EXPECT_NOTIFICATION
- EXPECT_ANY
- EXPECT_ANY_SESSION_NOTIFICATION
- EXPECT_EVENT

### HMI side
- EXPECT_HMIRESPONSE
- EXPECT_HMINOTIFICATION
- EXPECT_HMICALL
- EXPECT_HMIEVENT

## Expectation extensions
Expectations may be extended with some extra specifications. They are intended to be used in call chain: programmer can improve expectation parameters by calling following methods one after one.
Example:
```
EXPECT_HMINOTIFICATION("OnHMIStatus")
:Timeout(5000)
:Times(AnyNumber())
:Do(function() print ("OnHMIStatus received") end)
```
- Times
- Do, DoOnce
- Timeout
- Pin, Unpin
- ValidIf

## Services
In order to start or stop service following functions are used:
- StartService
- StopService

## Media streaming
ATF allows to start media streaming in background. Use `mobileSession:StartStreaming(service, filename, bandwidth)` to start media streaming. Optional `bandwidth` argument sets maximum bandwidth of streaming (bytes per second). Default is 30 kbps. Note that the service should be started before StartStreaming is called.
Example:
```
self.mobileSession:StartService(10)
:Do(function() self.mobileSession:StartStreaming(10, "video.mpg", 30 * 1024)
```
To stop file streaming, call `StopStreaming(filename)`.

## Auxiliary functions

## Reports and Logs
