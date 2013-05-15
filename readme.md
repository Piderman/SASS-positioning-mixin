<h1>Shorthand positioning mixin</h1>
<p>Uses the same syntax as a margin/padding to set properties for <code>top | right | bottom | left</code> of an element</p>
<p>Generally you are setting at least two offsets when positioning along with its position type</p>

<h2>Examples</h2>
<pre><code>
.arrow { @include pos(a, 5px null null -10px); }
.arrow { position: absolute; top: 5px; left: -10px; }

//anchor some text to the bottom on an element
.caption { @include pos(ab, null 0 0); }
.caption { position: absolute; right: 0; bottom: 0; left: 0; }

//full screen modal
.modal { @include pos (a, 0); }
.modal { position: absolute; top: 0; right: 0; bottom: 0; left: 0; }

//remove any previous offsets 
.main-nav {
	@include pos(a, 0 null null -100%);
	
	&.active { left: 0; }
}

@media (min-width: 40em) {
	//needs relative for absolute children, but remove any offset
	.main-nav { @include pos (r, auto);}
}
</code></pre>