# TodoList 클론 코딩 
- 패스트캠퍼스 iOS 앱 개발 올인원 패키지 Online 클론코딩 

<img src ="https://user-images.githubusercontent.com/26668309/146727700-9158bab8-313f-4728-9933-b8c6f131b537.png" width = 30%> <img src = "https://user-images.githubusercontent.com/26668309/146727231-612407fe-c30a-44a0-aedb-f4bace7d7557.png" width = 30% >


# 사용요소 
- NotificationCenter, UICollectionReusableView, CollectionView 
- Storyboard


# 새로 배운 내용
 
  - 키보드디텍션

  ```Swift
  NotificationCenter.default.addObserver(self, selector: #selector(adjustInputView)
       , name: UIResponder.keyboardWillShowNotification, object: nil)

  NotificationCenter.default.addObserver(self, selector: #selector(adjustInputView)
     , name: UIResponder.keyboardWillHideNotification, object: nil)         


extension TodoListViewController {
    @objc private func adjustInputView(noti: Notification) {
        guard let userInfo = noti.userInfo else { return }
        // TODO: 키보드 높이에 따른 인풋뷰 위치 변경
        guard let keyboardFrame = (userInfo[UIResponder.keyboardFrameEndUserInfoKey] as? NSValue)?.cgRectValue else { return }
        
        if noti.name == UIResponder.keyboardWillShowNotification {
            let adjustmentHeight = keyboardFrame.height - view.safeAreaInsets.bottom
            inputViewBottom.constant = adjustmentHeight
        } else {
            inputViewBottom.constant = 0
        }
    }
}
  ```

  - mutating , equatable 

  ```Swift
  struct Todo: Codable, Equatable {
    let id: Int
    var isDone: Bool
    var detail: String
    var isToday: Bool
    
    mutating func update(isDone: Bool, detail: String, isToday: Bool) {
        // TODO: update 로직 추가
        self.isDone = isDone
        self.detail = detail
        self.isToday = isToday
    }
    
    static func == (lhs: Self, rhs: Self) -> Bool {
        // TODO: 동등 조건 추가
        return lhs.id == rhs.id
    }
  }
  ``` 
  
  - enum CaseIterable 

  ```Swift
    enum Section: Int, CaseIterable {
        case today
        case upcoming
        
        var title: String {
            switch self {
            case .today: return "Today"
            default: return "Upcoming"
            }
        }
    }

   Section.allCases.count

  ``` 
