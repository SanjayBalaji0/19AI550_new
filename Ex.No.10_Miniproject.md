# Ex.No: 10  Implementation of 2D/3D Game

### REGISTER NUMBER: 212223240149

---

### AIM:

To develop a **2D Coin Collector Game** in Unity.

### Algorithm:

```text
1. Create a 2D game project in Unity.
2. Create the game environment with a player, coins, enemies and a destination.
3. Add Rigidbody2D and Collider2D components to the required game objects.
4. Write a C# script to control the player movement.
5. Detect collision between the player and coins.
6. Increase the score and destroy the coin when it is collected.
7. Add enemies and detect collision with the player.
8. Display Game Over when the player collides with an enemy.
9. Create a destination point and detect when the player reaches it.
10. Display the winning message after completing the required objective.
11. Run and test the game in the Unity Game window.
```

### Program:

```csharp
using UnityEngine;
using UnityEngine.SceneManagement;

public class CoinCollector : MonoBehaviour
{
    public float speed = 5f;
    public int score = 0;

    void Update()
    {
        float x = Input.GetAxis("Horizontal");
        float y = Input.GetAxis("Vertical");

        transform.Translate(new Vector2(x, y) * speed * Time.deltaTime);
    }

    private void OnTriggerEnter2D(Collider2D other)
    {
        if (other.CompareTag("Coin"))
        {
            score++;
            Destroy(other.gameObject);
            Debug.Log("Coins Collected: " + score);
        }

        if (other.CompareTag("Enemy"))
        {
            Debug.Log("Game Over");
            SceneManager.LoadScene(SceneManager.GetActiveScene().name);
        }

        if (other.CompareTag("Finish"))
        {
            Debug.Log("You Win! Coins Collected: " + score);
        }
    }
}
```

### Output:

<img width="978" height="537" alt="image" src="https://github.com/user-attachments/assets/187eab52-9e10-42f8-bd21-4b700b3a2721" />

<img width="962" height="548" alt="image" src="https://github.com/user-attachments/assets/2f268f26-7586-48fe-8969-65b75b897f8b" />


### Result:

Thus the **2D Coin Collector game** was successfully developed using Unity and adopted **Reinforcement Learning (AI) technology**.
