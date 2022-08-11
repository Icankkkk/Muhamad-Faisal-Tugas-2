# Muhamad-Faisal-Tugas-2
## Bug List

### Very high
- ```Assets\scripts\GameManager.cs(68,3): error CS0103: The name '_score' does not exist in the current context```
fix nya yaitu dengan merubah variabel _score menjadi score

- ```Assets\scripts\GameManager.cs(69,20): error CS0029: Cannot implicitly convert type 'int' to 'string'```
fix nya yaitu dengan mengconvert variabel score (int) kedalam string dengan cara ```score.ToString()``` 

### Medium
- ```NullReferenceException: Object reference not set to an instance of an object CountdownText+<Countdown>d__6.MoveNext() (at Assets/scripts/CountdownText.cs:32)```
fix nya dengan cara menambahkan event ```CountdownText.OnCountdownFinished += OnCountdownFinished;``` di dalam method ```OnEnable()``` yang terdapat pada  script GameManager

### High
- ```Ketika di click pesawat malah terbang ke bawah``` fix nya yaitu dengan mengganti ```rb.AddForce (Vector2.down * tapForce, ForceMode2D.Force);``` menjadi ```rb.AddForce (Vector2.up * tapForce, ForceMode2D.Force);``` pada input mouse yang terdapat pada method Update di script TapController

- ```Tag: DeadZones is not defined. UnityEngine.StackTraceUtility:ExtractStackTrace ()``` Fix nya yaitu dengan merubah tag ```DeadZones``` menjadi ```DeadZone``` pada ```TapController:OnTriggerEnter2D (UnityEngine.Collider2D) (at Assets/scripts/TapController.cs:86)```

- pesawat hanya mengapung, dan UI freeze ketika countdown selesai. Fix nya yaitu dengan merubah ```public bool GameOver { get { return !gameOver; } }``` menjadi ```public bool GameOver { get { return !gameOver; } }``` 

### Low
- Collider dan script ```TapController``` pada pesawat tidak aktif. Fix nya yaitu dengan meng enable kedua komponen tersebut pada inspector.
- ```Re-order operands for better performance``` fix nya adalah dengan merubah ```poolObjects [i].transform.position+= -Vector3.right * shiftSpeed * Time.deltaTime;``` menjadi ```poolObjects [i].transform.position+= shiftSpeed * Time.deltaTime * -Vector3.right;``` di method ```Shift()``` pada script ```Parallaxer.cs```
