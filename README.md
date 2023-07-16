# ToastBanner

How to use it ?
1. Apply your custom them class 

class CustomSettings:BannerTheme {

    var style: BannerStyle = .info
    
    var icon:UIImage?{
        switch style {
        case .error:
            return UIImage(systemName: "wrongwaysign")
        case .warning:
            return UIImage(systemName: "exclamationmark.triangle")
        case .info:
            return UIImage(systemName: "info.circle")
        }
    }
    
    var color:UIColor{
        switch style {
        case .error:
            return .systemRed
        case .warning:
            return .systemYellow
        case .info:
            return .label
        }
    }
    
    var backgorundColor: UIColor{
        switch style {
        case .error:
            return .systemRed
        case .warning:
            return .systemYellow
        case .info:
            return .label
        }
    }
    
    var iconColor: UIColor{
        switch style {
        case .error:
            return .systemRed
        case .warning:
            return .white
        case .info:
            return .label
        }
    }
    
    var textColor: UIColor{
        switch style {
        case .error:
            return .systemRed
        case .warning:
            return .white
        case .info:
            return .label
        }
    }
    
    var messageFont: UIFont = UIFont.systemFont(ofSize: 16)
    
    var titleFont:  UIFont = UIFont.systemFont(ofSize: 16 , weight: .medium)
    
    var time: Int = 10
    
    var iconSize: CGFloat = 32
    
}

2. setup your toast settings in app delegate 
  ToastBanner.shared.settings = BannerSettings(theme: CustomSettings())

3. show the toast where ever you want.
   ToastBanner.shared.show(message: "Apologies for the inconvenience. If the text fields are still", style: .info , position: .Bottom)
