# Storing_ValuesIn_UserDefaultSystem

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


