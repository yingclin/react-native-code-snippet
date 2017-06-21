# react-native-router-flux

## 基本用法

### 定義場景(畫面) Sence
```
<Router>
    <Scene key="login">
        <Scene key="loginForm" component={LoginForm} title="Login Form" />
    </Scene>
    <Scene key="member">
        <Scene key="memberList" component={MemberList} title="MemberList" />
        <Scene key="memberDetail" component={MemberDetail} title="MemberDetail" />
    </Scene>
</Router>
```
### 場景轉換

到指定場景：`Actions.[key]`
```
Actions.member();
```
轉換後重設(清除)瀏覽記錄
```
Actions.memberDetail({ type: 'reset' });
```
回到前一個場景：`Actions.pop()`

傳資料給場景：
```
Actions.memberDetail({ message: 'Hello Detail' });
Actions.memberDetail({ type: 'reset', message: 'Hello Detail' });
```
* MemberDetail 可取得 message，如：`<Text>{this.props.message}</Text>`  
* `type`：為　react-native-router-flux　保留字

## Tab

###
```
<Router>
    <Scene
        key="tabbar"
        tabs
        tabBarStyle={{ backgroundColor: '#FFFFFF' }}
    >
        {/* Tab and it's scenes */}
        <Scene key="tab1" title="OSU" icon={TabIcon}>
            <Scene
                key="scarlet"
                component={ScarletScreen}
                title="Scarlet"
            />
            <Scene
                key="gray"
                component={GrayScreen}
                title="Gray"
            />
        </Scene>
　　　　{/* 多個 Tab，就設多組 */}
　　　　<Scene key="tab2" ...
    </Scene>
</Router>
...
const TabIcon = ({ selected, title }) => {
    return (
        <Text style={{ color: selected ? 'red' : 'black' }}>{title}</Text>
    );
};
```
