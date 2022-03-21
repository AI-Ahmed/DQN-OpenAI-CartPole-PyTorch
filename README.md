# <p align='center' style='color:DarkSlateBlue'> <font size=6 color='DarkSlateBlue'>Deep Q-Network - Reinforcement Learning with PyTorch</font></p>

- <font color='gray'>Reinforcement Learning - Developing Intelligent Agents</font>
- <font color='gray'>Deep Learning Course 5 of 6 - Level: Advanced</font>

- Ref: [DeepLizard – Reinforcement Learning - Developing Intelligent Agents](https://www.youtube.com/playlist?list=PLZbbT5o_s2xoWNVdDudn51XM8lOuZ_Njv)
- 
## 📚<font size=5 color='CornflowerBlue'><a href='https://deeplizard.com/learn/video/FU-sNVew9ZA'>Project overview</a></font>

We're going to be building and training a deep Q-network to learn to balance a pole on a moving cart. This is widely known as the cart and pole problem. 

We'll be using **OpenAI's Gym** toolkit to set up our cart and pole environment. 

<p align='center'>
<img align='center' src='https://deeplizard.com/assets/svg/ac9a374b.svg'/>
<p align='center'>Image Snapped from <a href ='https://deeplizard.com/learn/video/FU-sNVew9ZA'>Deeplizard</a>
</p>

<p align='center'>
<img align='center' src='https://static.packt-cdn.com/products/9781789345803/graphics/assets/9170409d-15f1-453b-816a-6f601a89fcf2.png'/>
<p align='center'>Image Snapped from <a href ='https://subscription.packtpub.com/book/data/9781789345803/8/ch08lvl1sec46/introducing-cartpole-v1'>Packt – Hands-On Q-Learning with Python</a>
</p>

---
## <font size='5' color='CornflowerBlue'>🄠-Learning Algorithm</font>

1. Initialize replay memory capacity.
2. Initialize the **policy network** with random weights.
3. Clone the **policy network**, and call it the **target network**.

4. For each episode:
  - Initialize the starting state.
  - For each time step:
    1. Select an action.
      - *Via exploration or exploitation*
    
    2. Execute selected action in an emulator.
    
    3. Observe <u>reward</u> and <u>next state</u>.
    
    4. Store experience in <u>replay memory</u>.
    
    5. Sample random batch from replay memory.
    
    6. Preprocess states from batch.
    
    7. Pass batch of preprocessed states to **policy network**.
    
    8. <u>Calculate loss</u> between output Q-values and target Q-values.
      - *Requires a pass to the **target network** for the next state*
    
    9. Gradient descent updates weights in the **policy network** to minimize loss.
             
      - *After `x` time steps, weights in the **target network** are <u>updated to the weights</u> in the **policy network**.*
