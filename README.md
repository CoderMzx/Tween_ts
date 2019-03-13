# Tween_ts

将egret 中的 tween 移植出来，可供cocos-creator typescript项目使用
### usage example
```
import { Tween, Ease } from "./tween";

const { ccclass, property } = cc._decorator;

@ccclass
export default class Helloworld extends cc.Component {

    @property(cc.Label)
    label: cc.Label = null;

    @property
    text: string = 'hello';

    start() {
        // init logic
        this.label.string = this.text;

        Tween.removeTweens(this.label.node);
        Tween.get(this.label.node, { loop: true }).to({ y: 100, opacity: 150 }, 1.25, Ease.backInOut).to({ y: -180, opacity: 255 }, 1);
    }

    update(dt: number) {
        Tween.tick(dt);
    }
}

```
