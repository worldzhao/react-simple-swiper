✨ 年轻人的第一个轮播图组件

💗 开发/测试/发布流程见该文章：[简书](https://www.jianshu.com/p/db6113c94dbc)

😊 本项目仓库地址[Github](https://github.com/worldzhao/react-tiny-swiper)

第一次封装组件，肯定有许多边界问题没有考虑到，如果出现问题，欢迎给我提 issue。

## API
| Property         | Description                               | Type   | Default   | Optional                      |
| ---------------- | ----------------------------------------- | ------ | --------- | ----------------------------- |
| width            | container width                           | number | 730       |
| height           | container height                          | number | 336       |
| autoplay         | switch automatically                      | bool   | true      | true,false                    |
| autoplayInterval | automatic switch interval(ms)             | number | 3000      |
| dots             | whether to show the page button below     | bool   | true      | true,false                    |
| dotsColor        | page button color                         | string | '#31A896' | any css color value in string |
| dotsSize         | page button size                          | string | 'normal'  | 'normal','small' , 'large'    |
| arrows           | whether to show flip button on both sides | bool   | true      | true, false                   |
| arrowsType       | flip button color                         | string | 'light'   | 'dark' , 'light'              |
| onChange         | switch callback                           |

## 可选参数：

```js
static propTypes = {
    width: PropTypes.number,
    height: PropTypes.number,
    autoplay: PropTypes.bool,
    autoplayInterval: PropTypes.number,
    dots: PropTypes.bool,
    dotsColor: PropTypes.string,
    dotsSize: PropTypes.oneOf(['normal', 'small', 'large']),
    arrows: PropTypes.bool,
    arrowsType: PropTypes.oneOf(['dark', 'light']),
    onChange: PropTypes.func,
  };
```

## 基本使用：

* npm

```
npm install react-tiny-swiper
```

```js
import toolbox from "react-tiny-swiper";
const { Swiper } = toolbox;
const renderSwiper = items => {
  const setting = {
    width: 730,
    height: 336,
    autoplay: true,
    autoplayInterval: 3000,
    arrows: true,
    arrowsType: "light",
    dots: true,
    dotsColor: "red",
    dotsSize: "normal"
  };
  return (
    <Swiper {...setting}>
      {items.map(item => (
        <div key={item.imgurl}>
          <img src={item.imgurl} alt="swiper" />
        </div>
      ))}
    </Swiper>
  );
};
```
