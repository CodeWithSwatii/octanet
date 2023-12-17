function addTask() {
  var taskInput = document.getElementById('taskInput');
  var priority = document.getElementById('priority');
  var dueTime = document.getElementById('dueTime');
  var taskList = document.getElementById('taskList');

  if (taskInput.value.trim() === '') {
    alert('Please enter a task.');
    return;
  }

  var li = document.createElement('li');

  // Create a timestamp
  var timestamp = new Date();
  var formattedTimestamp = timestamp.toLocaleString();

  // Append task text, priority, due time, and timestamp to the list item
  li.appendChild(document.createTextNode(
    taskInput.value +
    ' - Priority: ' + priority.value +
    ' - Due Time: ' + (dueTime.value || 'Not specified') +
    ' - ' + formattedTimestamp
  ));

  taskList.appendChild(li);

  // Clear input fields
  taskInput.value = '';
  priority.value = 'important';
  dueTime.value = '';
}
