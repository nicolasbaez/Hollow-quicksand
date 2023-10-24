# Hollow-quicksand
Al we need is love

![buh](https://github.com/nicolasbaez/Hollow-quicksand/blob/main/xp016.gif)
```javascript
w = k = 500;
h = w / 2;
setup = (_) => createCanvas(w, w, WEBGL);
draw = (_) => {
  clear();
  rotateY(k / 32);
  r = sin(k) * h;
  for (i = 0; i < 3; i += 0.3) {
    beginShape();
    for (j = 0; j < 6; j += 0.3) {
      n = noise(i, j, k);
      noStroke();
      fill(h, 0, 0, n * h);
      vertex(n * r * sin(i) * cos(j), n * r * sin(i) * sin(j), n * r * cos(i));
    }
    endShape();
  }
  k -= 0.05;
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp016.gif", 1920, { delay: 0, units: "frames" });
  }
};
