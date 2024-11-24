# 🧩 SnapKit Layout Helper 
A simple helper struct to apply flexible layout constraints using [SnapKit](https://github.com/SnapKit/SnapKit) with easy-to-use methods for common use cases. Perfect for building responsive layouts with minimal code.

# ✨ Features 
* 🧰 Apply Auto Layout constraints easily to any UIView.
* 🚀 Flexible top, bottom, leading, and trailing offsets relative to a superview's safe area.
* 🔧 Support for additional custom constraints with closures.
* 💡 Quick to integrate into any SnapKit-based project.

# 🔧 Installation 
To get started, simply add SnapKit to your project via CocoaPods, or Swift Package Manager. Then, you can use this layout helper in your project.

# 📝 Example Usage
Here’s a simple example of how to use LayoutConstraints:
```swift
import SnapKit

class ViewController: UIViewController {
    let myView = UIView()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        view.addSubview(myView)
        
        LayoutConstraints.applyLayoutConstraints(myView, view: self.view, topOffset: 20, leadingOffset: 15) { make in
            make.height.equalTo(100)
            make.width.equalTo(200)
        }
    }
}
```

**This will apply the following constraints to myView**:
* 20pt top offset relative to the safe area of the superview.
* 15pt leading offset.
* Additional custom constraints for height and width.

# 🔄 Customization 
You can easily customize the layout by passing different values for topOffset, leadingOffset, bottomOffset, and trailingOffset. You can also add your own custom constraints using the closure parameter.


