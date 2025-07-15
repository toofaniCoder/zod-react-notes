# 📄 Zod File Validation Example

This example demonstrates how to validate an uploaded file using Zod. It ensures that:

- The file size is at least 500KB
- The file size is less than 900KB
- The file type must be PNG or JPEG

```js
import * as z from "zod";

const fileSchema = z.object({
  profile: z
    .file()
    .min(500_000, {
      message: "Profile picture must be at least 500KB.",
    })
    .max(900_000, {
      message: "Profile picture must be less than 900KB.",
    })
    .mime(["image/png", "image/jpeg"], {
      message: "File must be in PNG or JPEG format.",
    }),
});

```
