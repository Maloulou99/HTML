```mermaid
    classDiagram
        WishlistController "1..*" o--> "1" WishlistRepository
        LoginRepository "1" <--o "1" LoginController
        WishlistController "1" o--> "1" LoginController
        Wish "1" <.. "0..*" User
        User "1..*" <.. "1" WishlistRepository
        Wish "1..*"..> WishlistRepository
        WishlistController "1" ..> "0..*" Wish
        LoginRepository .. WishlistRepository
        
        
        

        class User{
            +userId: int
            +firstName: String
            +lastName: String
            +email: String
            +password: String

            +getUserId()
            +getFirstName()
            +getLastName()
            +getEmail()
            +getPassword()

            +setFirstName()
            +setLastName()
            +setEmail()
            +setPassword()
        }

        class Wish{
            +wishId: int
            +titel: String
            +description: String
            +url: String
            +userId: int

            +getWishId()
            +getTitle()
            +getDescription()
            +getUrl()
            +getUserId()

            +setTitle()
            +setDescription()
            +setUrl()
        }

        class WishlistController{
            +repository: WishlistRepository

            +landingPage()
            +createUser()
            +addUser()
            +mainPage()
            +createWish()
            +addWish()
            +updateWish()
            +updateUserWish()
            +deleteWish()
        }

        class WishlistRepository{
            +url: String
            +user_id: String
            +user_pwd: String

            +createUser()
            +getUser()
            +createWish()
            +getWishlist()
            +getSpecificWish()
            +updateWish()
            +deletetWish()
        }

        
           class LoginController{
            +repository: LoginRepository
            +current_user: int

            +isLoggedIn()
            +landingPage()
            +showLogin()
            +login()
            +logout()
        }

         class LoginRepository{
            +url: String
            +user_id: String
            +user_pwd: String

            +checkEmail()
        }

      


``` 