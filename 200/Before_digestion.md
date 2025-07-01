import os

folder = "photo_before"
out_lines = []
for fn in sorted(os.listdir(folder)):
    if fn.lower().endswith(".jpg"):
        out_lines.append(f"![{fn}]({folder}/{fn})")
        out_lines.append(f"*{fn}*")
        out_lines.append("")   # blank line

with open("image-gallery.md", "w") as f:
    f.write("\n".join(out_lines))

