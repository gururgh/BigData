# BigData

# Acceso mediante reconocimiento facial.

### Cool Matú Miguel Alejandro.
## Gurubel Romero Javier Jeremias.
# Suarez Alonzo Fernando Enrique.


<code>
<flowchart>
<start>
			<id>s01</id>
			<label>Lamp doesn't work</label>
			<color>pink</color>
			<x>200</x>
			<y>5</y>
			<width>140</width>
			<height>60</height>
</start>
<decision>
			<id>d01</id>
			<label>Lamp plugged in?</label>
			<color>yellow</color>			
			<x>230</x>
			<y>110</y>
			<width>70</width>
			<height>70</height>
</decision>
		<end>
			<id>e01</id>
			<label>Plug in lamp</label>
			<color>lightgreen</color>			
			<x>400</x>
			<y>110</y>
			<width>140</width>
			<height>60</height>
                        </end>
		<decision>
			<id>d02</id>
			<label>Bulb burned out?</label>
			<color>yellow</color>			
			<x>230</x>
			<y>255</y>
			<width>70</width>
			<height>70</height>
                        </decision>
		<end>
			<id>e02</id>
			<label>Replace bulb</label>
			<color>lightgreen</color>			
			<x>400</x>
			<y>255</y>
			<width>140</width>
			<height>60</height>
                        </end>
<end>
			<id>e03</id>
			<label>Repair lamp</label>
			<color>lightgreen</color>			
			<x>200</x>
			<y>390</y>
			<width>140</width>
			<height>60</height>
</end>
		<link>
			<id>l1</id>
			<source>s01</source>
			<destiny>d01</destiny>
			<color>magenta</color>
		</link>
		<link>
			<id>l2</id>
			<source>d01</source>
			<destiny>d02</destiny>
			<label>Yes</label>
			<color>red</color>
		</link>
		<link>
			<id>l3</id>
			<source>d01</source>
			<destiny>e01</destiny>
			<label>No</label>
			<color>steelblue</color>
		</link>
		<link>
			<id>l4</id>
			<source>d02</source>
			<destiny>e02</destiny>
			<label>Yes</label>
			<color>gold</color>
		</link>
		<link>
			<id>l5</id>
			<source>d02</source>
			<destiny>e03</destiny>
			<label>No</label>
			<color>darkcyan</color>
		</link>				
</flowchart>
</code>
