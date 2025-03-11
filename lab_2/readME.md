# lab 2
## online compiler link
https://codesandbox.io/p/devbox/agitated-ace-vjf2kd?workspaceId=ws_JQbqGnwrH2NZkuQsobLimv

## video
<video controls src="video.mp4" title="video"></video>

## Screenshots
![alt text](image.png)
![alt text](image-1.png)
![alt text](image-2.png)
![alt text](image-3.png)

## code

```js
import React, { useState } from "react";
import { View, Text, TextInput, Button, FlatList, StyleSheet } from "react-native";
import "react-native";

export default function App() {
  const [task, setTask] = useState(""); // Stores the new task
  const [tasks, setTasks] = useState([]); // Stores the list of tasks

  function addTask() {
    if (task.trim() !== "") { // Avoid empty tasks
      setTasks([...tasks, task]); // Add new task to list
      setTask(""); // Clear input
    }
  }

  return (
    <View style={styles.container}>
      <Text style={styles.title}>To-Do List</Text>
      <TextInput
        style={styles.input}
        placeholder="Enter a task"
        value={task}
        onChangeText={setTask}
      />
      <Button title="Add Task" onPress={addTask} color="#7D2689"/>
      
      <FlatList
        data={tasks}
        renderItem={({ item }) => <Text style={styles.task}>{item}</Text>}
        keyExtractor={(item, index) => index.toString()}
      />
    </View>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, padding: 20, justifyContent: "center",backgroundColor:"black" },
  title: { fontSize: 24, fontWeight: "bold", marginBottom: 10,color:"white" },
  input: { borderWidth: 3, padding: 10, marginBottom: 10,borderColor:"#7D2689",color:"white",fontWeight: "bold" },
  task: { fontSize: 18, padding: 5, borderBottomWidth: 1,color:"white" },
});

```

## Colors and fonts
### colors
1. violet **#7D2689**
2. white
3. black

### fonts
default
