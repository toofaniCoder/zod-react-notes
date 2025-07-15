# 📄 Zod File Validation Example

This example demonstrates how to validate an uploaded file using Zod. It ensures that:

- The file size is at least 500KB
- The file size is less than 900KB
- The file type must be PNG or JPEG

```js
const fileSchema = z.object({
  profile: z
    .instanceof(File)
    .refine((file) => file.size >= 500_000, {
      message: "Profile picture must be at least 500KB.",
    })
    .refine((file) => file.size < 900_000, {
      message: "Profile picture must be less than 900KB.",
    })
    .refine((file) => ["image/png", "image/jpeg"].includes(file.type), {
      message: "File must be a PNG or JPEG image.",
    }),
});
```
