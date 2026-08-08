# Guide: Font Scaling & UI Optimization for Dashboards and Modals

This guide documents the design pattern and technical approaches used to scale down typography and UI components on the customer side of LiteFi. Follow this reference when optimizing pages, modals, or components for consistent typography, visual hierarchy, and mobile layout fit.

---

## 1. Font Size Mapping Table
When scaling down pages/components for a more compact, dashboard-friendly layout, map standard Tailwind font-size classes to their scaled-down equivalents:

| Element Role | Original Size Class | Scaled Size Class | Pixel Equivalent (approx.) |
| :--- | :--- | :--- | :--- |
| **Page Title / Large Hero** | `text-2xl` / `text-3xl` | `text-xl` / `text-2xl` | 20px / 24px |
| **Modal Header / Card Title** | `text-lg` sm:`text-xl` | `text-base` sm:`text-lg` | 16px / 18px |
| **Body / Description / Form Labels** | `text-sm` sm:`text-base` | `text-xs` sm:`text-sm` | 12px / 14px |
| **Secondary Info / Box Subtext** | `text-xs` sm:`text-sm` | `text-[11px]` sm:`text-xs` | 11px / 12px |
| **Tags / Badges / Micro-Labels** | `text-[10px]` sm:`text-xs` | `text-[9px]` sm:`text-[10px]` | 9px / 10px |

---

## 2. Accompanying Spacing & Padding Scale
Font scaling is most effective when paired with scaled-down padding and spacing to preserve visual proportions:

* **Modal Padding**: Change `p-6` or `p-5` to `p-4 sm:p-5` (or `p-4 sm:p-6` for details dialogs).
* **Inner Gaps**: Change vertical container spacing from `space-y-6` to `space-y-4` or `space-y-3`.
* **Margins**: Reduce bottom margins on headings from `mb-4` or `mb-3` to `mb-2` or `mb-1.5`.

---

## 3. Icon & Graphic Sizing Rules
Icons and surrounding visual graphics should scale proportionally to the surrounding text sizes:

* **Header Icons**: Reduce container from `p-2` to `p-1.5` and icons from `h-5 w-5` to `h-3.5 w-3.5 sm:h-4 sm:w-4`.
* **Inline Indicators**: Reduce from `h-4 w-4` to `h-3 w-3 sm:h-3.5 sm:w-3.5` to avoid breaking alignments on small screens.

---

## 4. Example: Before vs. After
### Before (Large/Default)
```tsx
<DialogTitle className="flex items-center gap-3 text-lg sm:text-xl font-bold">
  <Shield className="h-4 w-4 sm:h-5 sm:w-5" />
  Check Credit Report
</DialogTitle>
<DialogDescription className="text-sm sm:text-base">
  You're about to check your credit report.
</DialogDescription>
```

### After (Scaled Down & Optimized)
```tsx
<DialogTitle className="flex items-center gap-2 text-base sm:text-lg font-bold">
  <Shield className="h-3.5 w-3.5 sm:h-4 sm:w-4" />
  Check Credit Report
</DialogTitle>
<DialogDescription className="text-xs sm:text-sm">
  You're about to check your credit report.
</DialogDescription>
```
