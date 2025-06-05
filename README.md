🔫 Гармата має обертатися за курсором.

💥 Куля з'являється з кінця гармати (firePoint).

🖱️ Стріляємо при натисканні лівої кнопки миші.

🔧 Крок 1: Підготуй firePoint
Усередині об'єкта Гармата створюємо новий порожній GameObject.

Назви його firePoint.

Перемісти його у сцені прямо на кінець ствола гармати (звідки має вилітати куля).

🧠 Крок 2: Скрипт Shooting.cs
Цей скрипт додай до гармати:
using UnityEngine;

public class Shooting : MonoBehaviour
{
    public GameObject bulletPrefab; // Префаб кулі
    public Transform firePoint;     // Точка вильоту

    public float bulletForce = 20f;

    void Update()
    {
        if (Input.GetMouseButtonDown(0)) // ЛКМ
        {
            Shoot();
        }
    }

    void Shoot()
    {
        GameObject bullet = Instantiate(bulletPrefab, firePoint.position, firePoint.rotation);
        Rigidbody2D rb = bullet.GetComponent<Rigidbody2D>();
        rb.AddForce(firePoint.right * bulletForce, ForceMode2D.Impulse);
    }
}




Крок 3: Налаштуй в Unity
Виділи гармату.

У полі Shooting (Script):

Bullet Prefab — перетягни сюди префаб кулі.

Fire Point — перетягни сюди об'єкт firePoint.

🧪 Готово до тесту!
✅ Гармату можна крутити за мишкою (з GunController.cs)
✅ При натисканні ЛКМ — куля вилітає з кінця гармати з фізикою
