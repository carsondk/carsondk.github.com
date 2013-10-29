---
layout: post
title: "Hello World"
description: ""
category: ""
tags: []
---
{% include JB/setup %}


Thanks for visiting. Here is some code!

{% highlight objc linenos %}
- (void) onEnterFrame:(SPEnterFrameEvent *)event {
self.x += xVel;
self.y += yVel;
if (self.y > Sparrow.stage.height-self.height) {
yVel = -yVel;
self.y = Sparrow.stage.height-self.height;
} else if (self.y < 0) {
yVel = -yVel;
self.y = 0;
}
if (self.x > Sparrow.stage.width-self.width) {
//xVel = -xVel;
[self reset];
// fire off right loss
[self dispatchEvent:[SPEvent eventWithType:EVENT_TYPE_RIGHT_LOSS bubbles:YES]];
} else if (self.x < 0) {
//xVel = -xVel;
[self reset];
// fire off left loss
[self dispatchEvent:[SPEvent eventWithType:EVENT_TYPE_LEFT_LOSS bubbles:YES]];
}
}
{% endhighlight %}
