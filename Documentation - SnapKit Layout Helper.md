# Documentation - SnapKit Layout Helper

## Description
**SnapKit Layout Helper** is a framework for simplified application of Auto Layout constraints to UI elements using the **SnapKit** library. It allows you to set indents and add additional constraints via closures.

## How to use
### A simple example:
```swift
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
### What will happen:
* The top indent of myView will be 20pt relative to the safe area of self.view.
* The left indent of myView will be 15pt relative to the safe area of self.view.
* The height of myView will be 100pt.
* The width of myView will be 200pt.

# Method parameters

### applyLayoutConstraints

* **element**
Type: UIView
The element to which the constraints will be applied.

* **view**
Type: UIView
The parent element to which the constraints will be applied.

* **topOffset**
Type: CGFloat? (optional)
The top indent relative to the safe area.

* **leadingOffset**
Type: CGFloat? (optional)
Left indent relative to the safe area.

* **trailingOffset**
Type: CGFloat? (optional)
Indentation on the right side of the safe area.

* **bottomOffset**
Type: CGFloat? (optional)
Indentation from the bottom relative to the safe area.

* **additionalConstraints**
Type: [((ConstraintMaker) -> Void)]
Constraints for adding custom constraints.

# Notes
1.If any of the indents (topOffset, leadingOffset, trailingOffset, bottomOffset) are not specified, the corresponding constraint will not be added.
2.Make sure the element is added to the view hierarchy (view.addSubview) before calling the method.
3.You can add any custom constraints via additionalConstraints closures.
