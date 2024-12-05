---
layout: essay
type: essay
title: ""
# All dates must be YYYY-MM-DD format!
date: 2024-12-04
published: false
labels:
  - React
  - TypeScript
  - Developer Tool Kit
---

```js
/* Container Component */
const EditGoalsForm = () => {
  // State and logic here
  return (
    <Container>
      {/* Presentational components */}
    </Container>
  );
};
```

```js
/* Presentational Component */
const GoalRow = ({ goal, onSave, onEdit }) => (
  <tr>
    <td>{goal.isEditing ? <FormControl ... /> : goal.goal}</td>
    <td>
      {goal.isEditing ? (
        <Button onClick={() => onSave(goal)}>Save</Button>
      ) : (
        <Button onClick={() => onEdit(goal)}>Edit</Button>
      )}
    </td>
  </tr>
);
```

```js
/* 
 * HOC Component 
 * File Location: @/lib/dbActions.ts
 */

export async function editGoal(goal: {
  id: number;
  goal: string;
  isEditing: number;
}) {
  // Update the database
  await prisma.goals.update({
    where: { id: goal.id },
    data: {
      goal: goal.goal,
      isEditing: goal.isEditing,
    },
  });
}
```

```js
/* Edit Goals Component */
'use client';

import { editGoal } from '@/lib/dbActions';
  .
  .
  .
const enableEdit = async (goal: Goals) => {
  const updatedGoal = { ...goal, isEditing: 1 };
  await editGoal(updatedGoal); // Calls HOC
  window.location.reload();
};

const saveGoal = async (goal: Goals) => {
  const updatedGoal = { ...goal, isEditing: 0 };
  await editGoal(updatedGoal); // Calls HOC
  window.location.reload();
};
  .
  .
  .
  <Button variant="success" className="me-2" onClick={() => saveGoal(goal)}>
    Save
  </Button>
  <Button variant="primary" className="me-2" onClick={() => enableEdit(goal)}>
    Edit
  </Button>
```