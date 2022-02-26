# TodoList 클론 코딩 
- 패스트캠퍼스 iOS 앱 개발 올인원 패키지 Online 클론코딩 

<img src ="https://user-images.githubusercontent.com/26668309/146727700-9158bab8-313f-4728-9933-b8c6f131b537.png" width = 30%> <img src = "https://user-images.githubusercontent.com/26668309/146727231-612407fe-c30a-44a0-aedb-f4bace7d7557.png" width = 30% >


# 사용요소 
- NotificationCenter, UICollectionReusableView ,CollectionView 
- Codable, MVVM 


# 새로 배운 것 
 
  - 키보드디
  
  NotificationCenter.default.addObserver(self, selector: #selector(adjustInputView)
                                      , name: UIResponder.keyboardWillShowNotification, object: nil)

  NotificationCenter.default.addObserver(self, selector: #selector(adjustInputView)
                                      , name: UIResponder.keyboardWillHideNotification, object: nil)
        
