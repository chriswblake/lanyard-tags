## Design your own 🎨
Missing a design you would like? Here is a guide to make your own!

### Tools and Materials
The following were the tools and materials used for creating the existing designs.
Naturally, you can use other tools and materials but your process may need some adapting.

- [Autodesk Fusion](https://www.autodesk.com/products/fusion-360/personal)
- [Bambu Labs P1S 3D Printer](https://bambulab.com/en-us/p1)
    - 0.4mm nozzle
- [Bambu Labs Automatic Material System (AMS)](https://us.store.bambulab.com/products/ams-multicolor-printing)
- [Bambu Studio](https://bambulab.com/en/download/studio)
- [PLA Filament](https://store.bambulab.com/products/pla-basic-filament)
- [NFC Stickers](https://www.amazon.com/gp/product/B0CPJBP3R7)

### Design Constraints
| Design Constraint | Reason |
| --- | --- |
| NFC sticker void thickness: 0.4mm | Prevents the print nozzle dragging in the filament on higher layers. |
| Min Text Font: 4pt | The text will become unreadable. |
| Min Text Character Spacing: 15 | Letters may touch causing text to be unreadable. |
| Do not remove NFC mark | Users need a reminder that the functionality is there. | 
| Max Colors: 4 | An AMS is required. Most do not have more than 4 colors. |
| Lanyard Width: 20mm | The back hook slightly pinches the lanyard to avoid slipping. |

### Printing Constraints
| Printing Constraint | Reason |
| --- | --- |
| Body Layer Height: 0.2mm | Models are designed with changes intervals of 0.2mm. Also, this is a common printing height.  |
| Hook Layer Height: 0.08mm | Hooks are cantilevers and would normally need supports. With the angle and lower layer height, suppports aren't needed. |
| Pause at layer 5 | An NFC sticker is manually placed in the void area. |

## 1. Make a Design
1. Look at the [existing designs](designs.md) to pick one that is similar to what you want.
1. Copy the existing design folder and modify the files.
    - Keep all files related to your design in that folder.
1. Open the `.f3d` file in Fusion 360.
    - Modify the design to your liking.
    - Follow the above design constraints to avoid quailty issues.
1. In Fusion 360, export the bodies as `.stl` files.
    - Tip: If you right-click the root component, you can export all visible bodies in one file. Hidden bodies will not be exported.

## 2. Prepare for Printing then Print
1. Open the existing `3mf` file in Bambu Studio (or Prusa Slicer).
1. At the top, select the  **Prepare** tab.
1. On the left, under the **Process** section, click the **Objects** view.
1. Find the existing design and expand it to show the internal `stl` files.
    - Example: `frame.stl`, `insert-white.stl`
    - Do not delete this design. It is already modified with adaptive layer heights.
1. Right click an `.stl` file and select **Replace with STL**. Select the files for your design.
1. At the top, select the **Preview** tab.
1. Ensure the layers look correct.
    - The nfc sticker void should be 2 layers (or lack of layers).
    - The text on the back should be 1 layer. Letters should not be touching.
    - The hook should be several thinners layers (0.08mm instead of 0.2mm).
1. Print the design! :)
    - It will pause before printing layer 5. Place the NFC sticker in the round pocket and resume printing.

## 3. (optional) Share your design
If you want to share your new design, submit a pull request. :)

1. Fork this repository.
    - This will create a copy of the repository in your account so you can freely modify it.
    - This will allow you to target your PR at this repository and pull updates from the original.
1. Export your design from Fusion 360 as a `.f3d` file. Add it to your design folder.
1. Take a real picture of your design, resized to 200x200 pixels. Name it `build-sample.jpg` and add it to your design folder.
1. Add the picture and its nam to the [designs](designs.md) list.
1. Create a pull request targeting the `main` branch.
    - Tip: Add a short description and any special notes to make it easier to review.
    - I will do a test print, and if it all works, I will merge your PR! (and add it to my lanyard) 🤓
