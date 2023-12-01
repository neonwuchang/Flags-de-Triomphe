## Description
Download this image file and find the flag. [Image](https://artifacts.picoctf.net/c/101/drawing.flag.svg)

![image](https://github.com/neonwuchang/Flags-de-Triomphe/assets/103783716/0ae78577-27b1-4c77-bb7f-cdd95e8dc5e8)

## Solution process
We are given an svg file. We examine the code, and notice this section:

```
id="text3723"><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.08501"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3748">p </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.08942"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3754">i </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.09383"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3756">c </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.09824"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3758">o </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.10265"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3760">C </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.10706"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3762">T </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11147"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3764">F { 3 n h 4 n </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11588"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3752">c 3 d _ 2 4 3 7 4 6 7 5 }</tspan></text>
```

There we have it! Contained within each `<tspan>` tag are the components of our flag:
- `id="tspan3748">p </tspan>`
- `id="tspan3754">i </tspan>`
- `id="tspan3756">c </tspan>`
- `id="tspan3758">o </tspan>`
- `id="tspan3760">C </tspan>`
- `id="tspan3762">T </tspan>`
- `id="tspan3764">F { 3 n h 4 n </tspan>`
- `id="tspan3752">c 3 d _ 2 4 3 7 4 6 7 5 }</tspan>`
  
Put it all together and we get the flag!
