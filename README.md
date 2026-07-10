# MK-10 Light Aircraft Design

Conceptual-through-structural design of the **MK-10**, a two-seat single-engine light aircraft, developed across a two-part aircraft design sequence (Aircraft Design I & II). The project carries a single design baseline from mission concept to a stress-analyzed, CAD-modeled three-view.

Inspired by the Tecnam P2002-JF · Low straight-tapered wing · Fixed tricycle landing gear

## Key Specifications

| Parameter | Value |
|---|---|
| Gross weight | 1,649.25 lb (748.09 kg) |
| Wing area | 126.52 ft² (11.75 m²) |
| Wingspan | 28.85 ft (8.79 m) |
| Wing airfoil | NACA 2415 |
| Tail airfoil | NACA 0012 |
| Aspect ratio | 6.58 |
| Powerplant | 125 BHP @ 2,550 rpm |

## Scope

- **Configuration & sizing** — mission definition, powerplant trade study, weight estimation and CG travel (FAR Part 23).
- **Aerodynamics** — airfoil selection and corrected characteristics, drag buildup.
- **Performance** — level flight, climb, ceilings, and range/endurance.
- **Loads & structures** — V-n flight envelope, gust and maneuvering load distributions, wing strip (spanwise) analysis, front/rear spar shear-moment sizing (per Bruhn, *Analysis and Design of Flight Vehicle Structures*), and landing-load cases.
- **Detailed design** — primary flight control surfaces and 3D CAD resolved into a final three-view.

## Repository Structure

```
mk10-aircraft-design/
├── README.md
├── .gitattributes                         # marks CAD files as binary
│
├── aerodynamics/
│   └── airfoils/
│       ├── naca-2415.txt                  # wing airfoil coordinates
│       └── naca-0012.txt                  # tail airfoil coordinates
│
├── analysis/                              # sizing, performance & structural calculations
│   ├── design-1-calculation.xlsx
│   ├── design-2-calculation.xlsx
│   └── plots/                             # exported performance & loads plots
│       ├── corrected-airfoil-characteristics.opju   # OriginLab source
│       ├── corrected-airfoil-characteristics.pdf
│       ├── corrected-airfoil-characteristics.png
│       ├── naca-2415-selected.png         # selected airfoil (drag polar)
│       ├── cg-travel-balance.png          # CG travel, % MAC
│       ├── power-required.png             # THP required vs V
│       ├── pa-pr.png                      # power available vs required
│       ├── climb-performance.png          # rate of climb vs V
│       ├── absolute-ceiling.png
│       ├── service-ceiling.png
│       └── vn-diagram.png                 # flight envelope
│
├── cad/                                   # SolidWorks native files (committed directly)
│   ├── fuselage/                          # Fuselage.SLDPRT
│   ├── wing/                              # 3D wing + front spar geometry
│   ├── empennage/                         # horizontal tail (NACA 0012)
│   ├── landing-gear/                      # gear geometry + landing conditions
│   ├── control-surfaces/                  # aileron, elevator, rudder, flaps
│   └── general-arrangement/               # side/top views + final three-view parts
│
└── drawings/                              # exported PDFs
    ├── three-view.pdf
    ├── spars/                             # front/rear spar dimensions, shear & moment
    ├── loads/
    │   ├── load-distributions/            # maneuvering, max fwd/aft conditions I–IV
    │   ├── wing-strips/                    # spanwise strips 1–10
    │   └── landing-conditions/             # level, nose-wheel-clear, tail-down
    ├── landing-gear/                      # turnover angle, wheel position, static load
    └── control-surfaces/                  # 3D-view exports
```

## Tools & References

- **CAD:** SolidWorks (parts, drawings)
- **Calculations:** Excel
- **Plotting:** OriginLab, Excel
- **Standards / references:** FAR Part 23; Bruhn, *Analysis and Design of Flight Vehicle Structures*
