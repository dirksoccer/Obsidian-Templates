```meta-bind-button
style: primary
label: Add Review
actions:
  - type: templaterCreateNote
    templateFile: z_Templates/Cigar_Review_Template.md
    folderPath: "The Humidor/Cigars/Reviews"
    fileName: <%tp.file.title%>
```