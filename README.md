# NBToastView
提示视图
效果图<还有很多设置,可以自行查看>
![tost展示图](https://github.com/NapoleonBaiAndroid/NBToastView/blob/master/NBToastView/test.gif "ToastView展示图")

## 使用方法
 
``` swift
    NBToast.show("显示message,其他默认配置")
    NBToast.show("显示message,停留1秒,其他默认", duration: 1)
    NBToast.show("显示message,等1秒显示,其他默认", delay: 1)
    NBToast.show("显示message,停留2秒,等1秒展示,支持展示完成回调", duration: 2, delay: 1, completion: {
        // 显示完成后回调
    })
    NBToast.show("显示message,支持回调,其他默认"){
        // 显示完成后回调
    }
    //如果需要进行属性配置,那么请看下方的配置属性
```

## NBToastView 配置属性
``` swift
    /// 显示文字颜色
    fileprivate static var s_textColor : UIColor             = UIColor.black
    /// 显示文字大小
    fileprivate static var s_textFont : UIFont               = UIFont.systemFont(ofSize: 17)
    /// 显示文字对齐方式
    fileprivate static var s_textAlignment : NSTextAlignment = NSTextAlignment.center
    /// 显示视图背景色
    fileprivate static var s_backgroundColor : UIColor       = UIColor.black.withAlphaComponent(0.5)
    /// 视图最大宽度设置
    fileprivate static var s_maxWidth : CGFloat              = 0.0
    /// 视图最大高度设置
    fileprivate static var s_maxHeight : CGFloat             = 0.0
    /// 文字显示最大行数
    fileprivate static var s_maxLines : UInt16               = 1
    /// 文字边距
    fileprivate static var s_paddingInsets : UIEdgeInsets          = UIEdgeInsets.zero
    /// 视图离顶部距离
    fileprivate static var s_marginTop : CGFloat             = TOAST_VIEW_MARGIN_TOP
    /// 视图离底部距离
    fileprivate static var s_marginBottom : CGFloat          = TOAST_VIEW_MARGIN_BOTTOM
    /// 视图圆角度
    fileprivate static var s_cornerRadius : CGFloat          = 0.0
    /// 视图显示时间
    fileprivate static var s_duration : TimeInterval       = TOAST_VIEW_SHOW_DURATION
    /// 视图在x秒后显示
    fileprivate static var s_delay : TimeInterval          = TOAST_VIEW_SHOW_DELAY
```
## 主要提供的展示函数
```swift
    /**
     自定义显示时间和延迟显示时间,并手动处理完成事件
     
     - parameter message:   显示文字
     - parameter duration:   显示时间
     - parameter delay:      延迟显示时间
     - parameter completion: 显示完成时回调
     */
    class func show(_ message:NSString , duration:TimeInterval = NBToast.s_duration, delay:TimeInterval = NBToast.s_delay, completion:CompLetion? = nil)
    
```
## 其他设置
 因为项目中大都是使用同一个提示背景颜色,文字颜色等配置,所以,可以将所有配置信息全部放入 Appdelegate 文件中,一次配置,终身受用!
 同时也提供了:
 ```swift
     /**
     将所有配置清除,恢复默认设置
     */
    class func restoredConfig()
 ```
 此函数用于清除之前配置的属性,恢复为默认的属性.

