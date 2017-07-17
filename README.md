# react-viewer-mda

[![NPM version][npm-image]][npm-url]
> react image viewer.

## Introduction

Because i can`t comfortable use [viewerjs](https://github.com/fengyuanchen/viewerjs) in react, so i create react-viewer to replace it.
This is a fork of [react-viewer](https://github.com/infeng/react-viewer).

**v2.2.5**
- Added `downloadable` option to image download.
- Hide navigation arrows when shows only one image.

**v2.2.6**
- Added afterChange property.
- Disable apropriate keyboard shortcuts when `zoomable` and `rotatable` is set to `false`.

## Installation

```bash
npm install react-viewer-mda --save
```

## Usage

```javascript
import * as React from 'react';
import Viewer from 'react-viewer-mda';
import 'react-viewer-mda/dist/index.css';

class App extends React.Component<any, any> {
  constructor() {
    super();

    this.state = {
      visible: false,
    };
  }

  render() {
    return (
      <div>
        <button onClick={() => { this.setState({ visible: !this.state.visible }); } }>show</button>
        <Viewer
        visible={this.state.visible}
        onClose={() => { this.setState({ visible: false }); } }
        images={[{src: '', alt: '', name: ''}]}
        />
      </div>
    );
  }
}
```

## Props

| props        | type                         | default | description                                                      | required |
|--------------|------------------------------|---------|------------------------------------------------------------------|----------|
| visible      | string                       |  false  | Viewer visible                                                   | true     |
| afterChange  | string                       |  noop   | Specify a function that will be called when active index changes | false    |
| onClose      | string                       |  -      | Specify a function that will be called when Visible close        | true     |
| images       | {src: string, alt: string}[] | []      | image source array                                               | true     |
| activeIndex  | number                       | 0       | active image index                                               | false    |
| zIndex       | number                       | 1000    | Viewer css z-index                                               | false    |
| container    | HTMLElement                  | null    | set parent node(inline mode)                                     | false    |
| drag         | boolean                      | true    | whether to drag image                                            | false    |
| attribute    | boolean                      | true    | whether to show image attribute                                  | false    |
| zoomable     | boolean                      | true    | whether to show 'zoom' buttom                                    | false    |
| rotatable    | boolean                      | true    | whether to show 'rotate' button                                  | false    |
| scalable     | boolean                      | true    | whether to show 'scale' button                                   | false    |
| downloadable | boolean                      | true    | whether to show 'download' button                                | false    |

## Keyboard support

- `Esc`: Close viewer.
- `←`: View the previous image.
- `→`: View the next image.
- `↑`: Zoom in the image.
- `↓`: Zoom out the image.
- `Ctrl + 1`: Reset the image.
- `Ctrl + ←`: Rotate left the image.
- `Ctrl + →`: Rotate right the image.


## License

MIT

[npm-image]: https://badge.fury.io/js/react-viewer-mda.svg
[npm-url]: https://npmjs.org/package/react-viewer-mda
