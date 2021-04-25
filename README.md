this version is still relatively simple, incomplete, and far from production-ready, but it includes some ideas for flexibility and architecture

the properties of the trade and quotes classes (MarketEvent types) are hard-coded because there are two types of messages and the sets of fields don't quite match - there are a few ways of dealing with that, but i chose to hard-code the expected sets of fields (per MarketEvent type) and their order to enforce consistency for the text file output - the data could be stored in a dictionary, and the set of expected fields and their order could be configurable, but that would not facilitate JSON serialization


todo:

use separate socket connections for each subscription, distribute load, add redundancy

listen to more events and log all activity (like subscriptions starting and stopping)

listen to heartbeat and add timer to try reconnecting until successful

include quotes (in addition to trades) and any other types of events that are of interest

include symbols other than futures, and generally explore API to figure out how to get more data

way to request replays from the API in case of outages (looks like sequence number can be used to specify ranges of historical data)

way to add and remove subscriptions dynamically, if that's desirable

use a windows service or need keep-alive system

add more logging destinations
