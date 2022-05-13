# chiefgroup-code-test-mobile-ios [![Build Status](https://app.bitrise.io/app/c6d58412d8d29b79/status.svg?token=ZQctxSUbgD27p5qqSamkRA&branch=master)](https://app.bitrise.io/app/c6d58412d8d29b79)

Code test for the Chief Group

# Technical Requirement, Tips

- VIPER
  - Views
    - CurrencyPairItemCell
    - CurrencyPairSectionHeader
    - MainTabBarViewController
    - MarketInfoHeaderView
    - MarketsViewController
    - NavigationViewController
  - Interactors
    - AccountInfoInteractor
    - CurrencyPairInteractor
  - Presenters
    - AccountInfoPresenter
    - CurrencyPairPresenter
  - Entity
    - AccountInfoModel
    - CurrencyPairModel
  - Router
    - AccountInfoRouter
    - CurrencyPairRouter
  - Protocol
    - AccountInfoView
    - CurrencyPairView

## Bonus

- MVVM [reference](https://github.com/kickstarter/ios-oss/blob/main/Kickstarter-iOS/ViewModels/UpdatePreviewViewModel.swift)

  - ViewModel
    - ViewModelOutputs
    - ViewModelInputs
      ...

- Programmatic UI/Layout is higher scores than Storyboard
- Unit tests for business logic module gets higher scores
- UI tests with [ios-snapshot-test-case](https://github.com/uber/ios-snapshot-test-case/) gets higher scores

# Sample UI

<img src="screen1.png" width="200"/>
<img src="screen2.png" width="200"/>
# Developer notes

- [ ] Setup Bitrise for pull request status checking
- [ ] Create Base VIPER classes
- [ ] Create VIPER modules
  - [ ] `CurrencyPair`
  - [ ] `AccountInfo`
- [ ] Setup Realm (model persistence)
- [ ] Setup Alamofire
- [ ] Create `MarketsViewController` with view model
  - [ ] Integration with VIPER callbacks and view model
- [ ] Create UI components
  - [ ] Tableview cell
  - [ ] Market info header view
  - [ ] Tab view controller
- [ ] UI + MVVM integration
- [ ] Skeleton view animation before data is load
- [ ] Unit testes

# Recommend Environment

Before running, developing and building the app, make sure your device's environment is suitable. We recommend the specification as follows:

- **macOS version >= 10.14**
- **Xcode version >= 10.1**
- **pod version >= 1.5.3**

# Build Step

1. Clone this repo by using SSH `$ git clone git@bitbucket.org:fishkingsin/chiefgroup-code-test-mobile-ios.git`
2. Open terminal and go to this project directory, then run `$ pod install --repo-update`
3. Use Xcode to open **ChiefGroupCodeTest.xcworkspace**, then specify the scheme. Finally, run it.

# Architecture

This project is broke down into two sections, business logic and screen logic.

1. For the business logic part, it is built using VIPER design pattern ~with my special favour~

   - Suggested reading:
     1. https://medium.com/cr8resume /viper-architecture-for-ios-project-with-simple-demo-example-7a07321dbd29)

2. For the screen logic part, I used Rx and MVVM (input-output + RxDriver pattern)
   - Suggested reading:
     1. https://medium.com/blablacar-tech/rxswift-mvvm-66827b8b3f10
     2. https://github.com/kickstarter/ios-oss/tree/master/Kickstarter-iOS/ViewModels
