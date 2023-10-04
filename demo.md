+ renderCenter
```
renderCenter={
              <View className="nav-bar-tab">
                <View className="nav-bar-tab-content" onClick={()=>this.props.store.navibarStore.changeNavIndex(0)}>
                  <View className={selected==0?'nav-bar-tab-content-text-selected':'nav-bar-tab-content-text'}>关注</View>
                  {selected==0&&<View className="nav-bar-tab-icon iconfont-caret-up icon-caret-up"></View>}
                </View>
                <View className="nav-bar-tab-content" onClick={()=>this.props.store.navibarStore.changeNavIndex(1)}>
                  <View className={selected==1?'nav-bar-tab-content-text-selected':'nav-bar-tab-content-text scale-50'}>推荐</View>
                  {selected==1&&<View className="nav-bar-tab-icon iconfont-caret-up icon-caret-up"></View>}
                </View>
              </View>
            }

```

+ css
```
.nav-bar-tab {
  width: 100%;
  height: 100%;
  display: flex;
  // justify-content: center;
  justify-content: space-around;
  align-items: center;
  width: 50%;
  /* prettier-ignore */
  // height: 32PX;
  height: 48PX;
  /* prettier-ignore */
  // border-radius: 16PX;
  position: relative;
  // background: #f6f6f6;
}

.nav-bar-tab-content{
  height: 100%;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content:center;
  align-items: center;
}

.nav-bar-tab-content-text{
  font-size:medium;
  // color: black;
}

.nav-bar-tab-content-text-selected{
  font-size: large;

}

.nav-bar-tab-icon{
  position: absolute;
  bottom: 0PX;
  // font-size: 30PX;
}

```
+ mobx
```
import { action, observable } from 'mobx'

class NavibarStore{
  @observable selected = 1;

  @action
  changeNavIndex(index) {
    this.selected = index;
  }

}



const navibarStore = new NavibarStore();

export default navibarStore
```

