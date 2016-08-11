
*react-websocket-flux*: React application over Websocket based on Flux

## Install

To setup the package.

```
npm install react-websocket-flux --save
```

## Quickstart

```
import { WebsocketStore, WebsocketActions } from 'react-websocket-view';

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

## License

The [MIT License](http://www.opensource.org/licenses/MIT) (MIT). See [LICENSE.md](LICENSE.md).
