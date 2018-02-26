# Publisher GameObject Kit

Publisher class for GameObject in Unity.

## Usage

### Publisher

Just extends Script class with Publisher

#### Example Usage

```cs
using PublisherKit;

public class ExamplePublisher : Publisher {

    const string EVENT_METHOD_NAME = "OnEvent";

	void Start () {
        Broadcast(EVENT_METHOD_NAME, "Sample Data");
	}

}

```

#### Broadcast Data

Broadcast(string methodName, object data=null)
* methodName: string - subscriber method name for receiving data
* data: object - data to send to subscriber. It can be of data

### Subscriber

Implement event receiver method and Register it as subscriber of publisher

#### Example Usage

```cs
using UnityEngine;

public class ExampleSubscriber : MonoBehaviour {

    public GameObject publisherObject;

	void Start () {
        publisherObject.GetComponent<ExamplePublisher>().Register(gameObject);
	}

    void OnEvent (string receiveData) {
        //Do something
    }

}
```

#### Register as Subscriber

```cs
publisherObject.GetComponent<ExamplePublisher>().Register(gameObject);
```

#### Handle Event Data

```cs
void OnEvent (string receiveData) {
    //Do something
}
```
