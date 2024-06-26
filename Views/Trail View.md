The Trail View shows all paths going _up_ from the current note. In this example, we see a binary tree going up two levels from the current note. The [[Codeblocks|Mermaid graph]] below visualises the same data:

%% TODO: Get a narrower link to Mermaid graph. Currently it's just to [[Codeblocks]] %%

![[view.page.trail.grid.png]]

> [!IMPORTANT]
> Read the Trail View from right-to-left. The right-most notes are the immediate neighbours of the current note. As you move further left, the notes get further away from the current note. Similar to how the File Explorer shows your current folder path from highest-to-lowest:
>
> ![[File Explorer Path Breadcrumbs.png]]

## Settings

Change under `Settings > Views > Page > Trail`

- **Enable**: Show/hide the Trail View at the top of your notes.
- **Field Groups**: Choose which [[Field Groups|field groups]] are shown. By default, the `ups` group is shown
- **Format**: Show the results in a Path/Grid format (the underlying data is still the same). %% TODO: Show example image %%
- **Path Selection**: Show all paths, or only the shortest/longest path.
- **Depth**: A maximum _depth_ of the paths. If the paths go longer than the max depth, slice them off.
- **Show Controls**: Show/hide a set of controls on top of the Trail View to change the above options.
- **No Path Message**: The message to show when there are no paths to show. Leave blank to show nothing.
