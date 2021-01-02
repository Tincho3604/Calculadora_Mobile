# Calculadora Mobile

_Mobile application developed in Widergy training. It is a mobile calculator, in which we can execute basic arithmetic operations, it has a history where operations can be saved. The history has delete functionalities to be able to delete all the history, and a button to delete each expression in particular. It also has the ability to edit the expressions and update them with a button._
_In another screen you can see a small survey, in which a user can leave a small return of the application registering with his username, his phone number and a field to leave a comment_

## Demo 📦

_To see a demo of the deployed project, you can go to [Project Demo]()_


### Installation 🔧

# Install dependencies for the client.
```
yarn install
```

## Starting 🚀
_Enter the repository folder_

_Then run_
```
yarn start
yarn android
```

_After completing these steps you will be able to view the project_


## Construido con 🛠️

_Tools that I used to create the project:_
* [React Native] (https://reactnative.dev/) - Framework used.
* [Redux] (https://es.redux.js.org/) - Used to work with a global state.
* [Redux-Form] (https://redux-form.com/8.3.0/) - Used to work with a general status and handling of forms.
* [Reactotron] (https://github.com/infinitered/reactotron) - Graphical interface to monitor the operation of the redux.
* [Apiary] (https://apiary.io/) - Tool to design, prototype, document and test APIs quickly.

## Code details_
_The endpoints are located in the actions folder and we use them to consume the APIs and dispatch the actions to the reducer_
```
import axios from 'axios'
import { Alert } from 'react-native'

export const saveExpression = (id, operation) => {  
      return async (dispatch, getState) => {
        const response = await axios.post(`https://private-4de685-martincumpe.apiary-mock.com/operation`,{id:id, operation:operation})
        const info = response.data
        if(info != null){
      
        Alert.alert(
          '¡El metodo POST se ejecuto correctamente!',
          '¡La operacion se registro con EXITO!',
          [
             {
              text: 'Cancel',
              onPress: () => console.log('Cancel Pressed'),
              style: 'cancel'
            },
            { text: 'OK', onPress: () => console.log('OK Pressed') }
          ],
          { cancelable: false }
        );    
      }

      dispatch({  
          type: 'SAVE_OPERATION',
            
            payload:{
              id:id,
              operation:operation
       }
    }); 
  }
}    
```


## Project screenshots 
![Captura de pantalla de 2020-12-12 21-54-13](https://user-images.githubusercontent.com/62455807/102000288-d6353580-3cc4-11eb-8be1-3c1eff88ab91.png)
![Captura de pantalla de 2020-12-12 21-45-39](https://user-images.githubusercontent.com/62455807/102000214-d54fd400-3cc3-11eb-8f50-b7d3ac1baac3.png)
![Captura de pantalla de 2020-12-12 21-50-04](https://user-images.githubusercontent.com/62455807/102000253-54450c80-3cc4-11eb-8a7a-358d254875c9.png)

## Authors ✒️

_Project carried out individually_

* ** Martin Cumpe ** - * Author *


## License 📄

All rights reserved.


## Expressions of Gratitude 🎁

* I thank the Widergy team, for the mentoring in my training process 🍺

