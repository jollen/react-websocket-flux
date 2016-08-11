
*react-websocket-flux*: React application over Websocket based on Flux

## Install

To setup the package.

```
npm install react-websocket-flux --save
```

## Quickstart

```
import { WebsocketStore, WebsocketActions } from 'react-websocket-flux';

export class MyApp extends Component {
    constructor(props, context) {
        super(props, context);

        this.onMessage = this.onMessage.bind(this);
        WebsocketActions.connect(this.props.server);
    }

    componentDidMount() {
        WebsocketStore.addMessageListener(this.onMessage);
    }

    componentWillUnmount() {
        WebsocketStore.removeMessageListener(this.onMessage);      
    }

    onMessage(data) {
        this.setState(data)
    }

    render() {
        return (    
            <div>
            </div>
        );
    }
}
```

## Usage

1. Import ```WebsocketStore``` and ```WebsocketActions``` from ```react-websocket-flux```.
2. Add ```onMessage``` callback method in your React component. For ES6, please bind ```this``` to ```onMessage```.
3. Invoke ```WebsocketActions.connect``` method to connect to Websocket server.
4. Invoke ```WebsocketStore.addMessageListener``` to register ```onMessage``` listener to Flux store

## License

The [MIT License](http://www.opensource.org/licenses/MIT) (MIT). See [LICENSE.md](LICENSE.md).
