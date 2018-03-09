## Triggering an avalanche of messages

1. The micro:bit should sometimes re-broadcast the message after it has received it. Use `randint` to choose a number and only transmit the message again if it matches a certain value.

1. Use `randint` again to include a slight pause of up to 5 seconds before re-transmission:

    ```python
    while True:
        if button_a.was_pressed():
            radio.send('now')

        message = radio.receive()
        if message == 'now':
            display.show(pic, delay=100, wait=False)
            sleep(300)
            display.clear()
            if random.randint(0, 9) == 0:
                sleep(random.randint(0,5000))
                radio.send('now')
     ```

1. Test your code as group. Depending on how many micro:bits are taking part, you should adjust the random values so that avalanches occur with a frequency you're happy with.

1. Work as a group to extend the project:

  - Modify the code that so pressing button B has a different effect
  - Can you coordinate your micro:bits so that pressing a button on one causes a text message to be displayed on the micro:bits one letter at a time?
