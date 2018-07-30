# bulkDump
for yaml dumps

Create a Single Story
{
  "Scope": "System (All Projects)",
  "AssetType": "Story",
  "Name": "Story"
}

create Multiple stories


- Scope: System (All Projects)
  AssetType: Story
  Name: Story A
- Scope: System (All Projects)
  AssetType: Story
  Name: Story B
  
  
  #Create multiple types of assets
  [{
  "Scope": "System (All Projects)",
  "AssetType": "Story",
  "Name": "Story A"
},
{
  "Scope": "System (All Projects)",
  "AssetType": "Defect",
  "Name": "Defect A"
}
]


#Create multiple Stories and attach Tests and Tasks to each
Scope: System (All Projects)
  AssetType: Story
  Name: Story-1
  Children:
  - AssetType: Test
    Name: Test-1 in Story-1
  - AssetType: Task
    Name: Task-1 in Story-1
  - AssetType: Test
    Name: Test-2 in Story-1
  - AssetType: Task
    Name: Task-2 in Story-1
- Scope: System (All Projects)
  AssetType: Story
  Name: Story-2
  Children:
  - AssetType: Test
    Name: Test-1 in Story-2
  - AssetType: Task
    Name: Task-1 in Story-2
  - AssetType: Test
    Name: Test-2 in Story-2
  - AssetType: Task
    Name: Task-2 in Story-2
- Scope: System (All Projects)
  AssetType: Story
  Name: Story-3
  Children:
  - AssetType: Test
    Name: Test-1 in Story-3
  - AssetType: Task
    Name: Task-1 in Story-3
  - AssetType: Test
    Name: Test-2 in Story-3
  - AssetType: Task
    Name: Task-2 in Story-3


#Create Story and attach to existing Epic
- from: Epic:4622
  update:
    Subs:
      add:
      - AssetType: Story
        Name: Story-1

#Create a new Story and use an existing Story then attach both to an Epic
---
- from: Epic:4622
  update:
    Subs:
      add:
      - AssetType: Story
        Name: Story-1
      - Story:1234


#Associate a Story to an Epic using a Subquery 
from: Epic:4622
  update:
    Subs:
      add:
        from: Story
        filter:
        - ID='Story:1227'






  
  
