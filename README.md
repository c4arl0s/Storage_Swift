# Storing_ValuesIn_UserDefaultSystem

1. [User Preferences]()
    * [User Defaults]()
2. [Files]()
    * [File Manager]()
    * [URLs and Paths]()
    * [Files and Directories]()
    * [Files Attributes]()
    * [Files Content]()
    * [Bundle]()
3. [Archiving]()
    * [Encoding and Decoding]()
    * [Real Life Application]()
    * [Quick Reference]()
    

Storing_ValuesIn_UserDefaultSystem

- Manage the preferences of our application.
- Only one UserDefault Object is assigned per application.
- It can store any amount of data, but it is recommender just to handle Strings and values.

``` swift
//
//  ViewController.swift
//  Storing_ValuesIn_UserDefaultSystem
//
//  Created by Carlos Santiago Cruz on 9/9/19.
//  Copyright © 2019 Carlos Santiago Cruz. All rights reserved.
//

import UIKit

class ViewController: UIViewController {
    @IBOutlet weak var stepper: UIStepper!
    @IBOutlet weak var counterLabel: UILabel!
    var defaultValues: UserDefaults!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        defaultValues = UserDefaults.standard
        if let number = defaultValues.object(forKey: "counter") as? Double {
            stepper.value = number
            counterLabel.text = String(number)
        }
    }

    @IBAction func didTappedOnPlusButton(_ sender: Any) {
        let current = stepper.value
        defaultValues.set(current, forKey: "counter")
        counterLabel.text = String(current)
    }
    
}
```

![Screen Shot 2019-09-09 at 9 25 48 PM](https://user-images.githubusercontent.com/24994818/64579401-6a894d80-d348-11e9-864f-d992c28dae59.png)
