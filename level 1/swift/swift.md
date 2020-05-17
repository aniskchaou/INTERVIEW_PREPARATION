

 **Who calls the main function of our app during the app launch cycle?**

 The main thread calls the main function of our app.

 **Which is the superclass of all the view controller objects?**

`UIViewController` class is the superclass of all the view controller objects. 

**What are the new feature in Swift 4.0?**



 - Faster and easier to use strings that keep Unicode correctness.
  
  
 - Tuples and multiple return values. 
 - Native error handling using
 - throw/try/catch. Extends to support serialization to a struct.
   
   

**Explain some `design patterns` which we normally use during the app development.**

**Behavioral:** Memento, and Observer.
**Creational:** Builder, Factory, and Singleton.
**Structural:** Façade, Adapter, and Decorator.

 **What mechanism does iOS support for multi-threading?**

`NSThread`: It can create `a low-level thread` which can be started by using the “start” method.
`NSOperationQueue`: It allows `a pool of threads` to be created and is used to execute “NSOperations” in parallel.

 **Explain Core Data**.

Core data is one of the most powerful frameworks provided by Apple for macOS and iOS apps. 

 **Explain MVC structure.**
MVC stands for the model view controller. MVC is a powerful software architecture pattern for using developing apps.

**Components**

**UICollectionView** 

 - une source de données UICollectionViewDataSource  
 -  diverses vues UICollectionViewCell
 -  un délégué UICollectionViewDelegate

**UITableView**


 - une source de données UITableViewDataSource un délégué
UITableViewDelegate
 - un contrôleur de vue sous-classe de UIViewController (ou UITableViewController) 

h

     class AuteursController: UITableViewController{
     //recuperer chaque cellule
            let cell = tableView.dequeueReusableCell(withIdentifier:"Cell")! as UITableViewCell
    }

**UISegmentedControl**

 **UISlider**
 
 **UISwitch**
 
**UITextFieldZone**

Classe UITextFieldZone d'édition textuelle mono-ligne entourée d'une figure rectangulaire

**UITextView**
Zone d'édition textuelle multi-ligne Sait faire défiler son contenu

**UIImageView**
Dessine d'une image ou d'une séquence d'images

**UILabel**
Affiche un texte non éditable
**UIImageView**

    var img:UIImageView!
    var myimage=UIImage(named: "Image")! 
    img.image=myimage

**UIView**
gère une surface rectangulaire dans la fenêtre de l'application

**Actions**

    class ViewController: UIViewController {
    @IBOutlet weak var statusLabel: UILabel!
    @IBAction func buttonPressed(sender: UIButton) {
    }
    }



**MVVM**
Le modèle-vue-vue modèle (en abrégé MVVM, de l'anglais Model View ViewModel) est une architecture et une méthode de conception utilisée dans le génie logiciel.
 le modèle MVC (modèle-vue-contrôleur), **`de séparer la vue de la logique et de l'accès aux données en accentuant les principes de binding et d’événement.`**

**ARC**
Le compilateur Swift utilise le comptage de référence automatique (ARC) le développeur **`n'a pas à se préoccuper de la libération de la mémoire, enfin presque Une variable normale de type classe garde une référence forte vers un objet`** 


(weak) : la variable **ne garde pas une référence forte vers l'objet**, ARC `peut libérer l'objet à tout instant` ; la variable peut prendre la valeur nil 

    weak var leader: Person? 

 
 (unowned) : **pas de référence forte, mais la variable ne peut jamais être nil** (Interruption logicielle si accès avec une valeur nil) 

    unowned let customer: Person

**Visibilité** 
**`private`**  entités visibles uniquement dans l'entité dans laquelle elles sont définies
**`fileprivate`**  entités visibles uniquement dans le fichier source dans lequel elles sont définies 
**`internal`**  entités visibles dans tout le module qui inclut leur définition (ex: application ou framework) 

**Transtypage vers une super-classe**

 **as** 

     let v = 3.14 as Double 

 **Transtype vers une sous-classe** 

 **as?**
 Retourne nil si le transtypage échoue if 

     let o = anObject as? ASubclass 

as! n'est à utiliser que si l'on est sûr que le transtypage réussisse, sinon erreur à l'exécution let o = anObject 

**as!** 
n'est à utiliser que si l'on est sûr que le transtypage réussisse, sinon erreur à l'exécution 

    let o = anObject as! ASubclass

 **is** 
 détermine si un object est une instance d'une certaine sous-classe 

     if anObject is AClass

**What is KVC and KVO?** 
**KVC** stands for Key-Value Coding. It's a mechanism by which `an object's properties can be accessed using string's at runtime` rather than having to statically know the property names at development time. 
**KVO** stands for Key-Value Observing and `allows a controller or class to observe changes to a property value`.

**How memory management is handled on iOS?**
ARC / MRC (manual) reference counting. Know strong, weak and assign.

**Could you explain what is the difference between Delegate and KVO?**
Both are ways to have relationships between objects.
 **Delegation is a one to one relationship** where one object implements a delegate protocol and another `uses it and sends messages to assuming that those methods are implemented` since the receiver promised to comply to the protocol. 
**KVO is many-to-many relationship** where one object `could broadcast a message and one or multiple other objects` can listen to it and react.

**What is a managed object context?**
First, managed object context is an instance of NSManagedObjectContext. **It is the central object in the Core Data stack.** It is used to create and fetch managed objects, and to manage undo and redo operations. 

**What is KVO?**
KVO stands for Key-Value Observing. It allows a controller or class to observe when a property value changes.

**What is the difference between frame and bound of a UIView?**
The frame of a UIView is the region **relative to the superview** it is contained within while the bounds of a UIView is the region relative to its **own coordinate system**.

**What is the `reuseIdentifier` for?**
The reuseIdentifier `indicates that cells for a UITableView` (or UICollectionView) can be reused. 

**What is Auto Layout?**
Auto Layout is used to dynamically calculate the size and position of views based on constraints.

**Segue**

present

show (push)

Show Detail (Replace)

Present as Popover
```
override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
    if (segue.identifier == "MainToTimer") {
        let vc = segue.destination as! YourViewController
        vc.verificationId = "Your Data"
    }
}
```
**web service**

    guard let url = URL(string: ”https://jsonplaceholder.typicode.com/todos") else {return}
    
    let task = URLSession.shared.dataTask(with: url) { (data, response, error) in
    
    guard let dataResponse = data,
              error == nil else {
              print(error?.localizedDescription ?? "Response Error")
              return }  
    
        do{ 
            //here dataResponse received from a network request 
            let jsonResponse = try JSONSerialization.jsonObject(with:
                                   dataResponse, options: []) 
            print(jsonResponse) //Response result 
         } catch let parsingError {
            print("Error", parsingError) 
       }
    
    }
    task.resume()
**Map kit**

    class MapController: UIViewController,CLLocationManagerDelegate {
    
        
        var locationManager=CLLocationManager()
        @IBOutlet weak var mapview: MKMapView!
        override func viewDidLoad() {
            super.viewDidLoad()
            mapview.showsUserLocation=true
            if CLLocationManager.locationServicesEnabled(){
                if CLLocationManager.authorizationStatus() == .restricted||CLLocationManager.authorizationStatus() == .denied ||
                    CLLocationManager.authorizationStatus() == .notDetermined{
                    locationManager.requestWhenInUseAuthorization()
                }
                
                locationManager.desiredAccuracy = 1.0
                locationManager.delegate = self
                locationManager.startUpdatingLocation()
                
                
                
            }else
            {
                print("please turn on your location service")
            }
            
        }
    
        func locationManager(_ manager: CLLocationManager, didFailWithError error: Error) {
            print("esrfefrserf")
        }
        
        func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
            let region=MKCoordinateRegionMake(CLLocationCoordinate2DMake(locations[0].coordinate.latitude, locations[0].coordinate.longitude),MKCoordinateSpanMake(0.2, 0.002) )
            self.mapview.setRegion(region, animated: true)
            
            
        }
**Core Data**

    func save(name: String) {
      
      guard let appDelegate =
        UIApplication.shared.delegate as? AppDelegate else {
        return
      }
      
      // 1
      let managedContext =
        appDelegate.persistentContainer.viewContext
      
      // 2
      let entity =
        NSEntityDescription.entity(forEntityName: "Person",
                                   in: managedContext)!
      
      let person = NSManagedObject(entity: entity,
                                   insertInto: managedContext)
      
      // 3
      person.setValue(name, forKeyPath: "name")
      
      // 4
      do {
        try managedContext.save()
        people.append(person)
      } catch let error as NSError {
        print("Could not save. \(error), \(error.userInfo)")
      }
    }
