<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<link rel="preconnect" href="https://fonts.gstatic.com/">
<meta name="viewport" content="width=device-width, user-scalable=no" />

<style>

	a:link {color: black; 		text-decoration: none;}
    a:visited {color: black;}
    a:hover {color: #4a4a4a;}
    a:active {color: black;}    /* selected link */
	
h1 {
		font-size: 50;
		font-family: 'Dosis', sans-serif;
		text-align: center;
	}
p {
		font-family: 'Roboto', sans-serif;
		text-align: center
	}
div {
		font-size: 21;
		font-family: 'Roboto', sans-serif;
		text-align: center;
	}
input[type=text], select {
		width: 60%;
		padding: 12px 20px;
		margin: 8px 0;
		  display: inline-block;
		border: 1px solid #ccc;
		border-radius: 40px;
		box-sizing: border-box;
}
input[type=submit] {
		width: 50%;
		background-color: #4CAF50;
		color: white;
		padding: 14px 20px;
		margin: 8px 0;
		border: none;
		border-radius: 40px;
		cursor: pointer;
}

input[type=submit]:hover {
		background-color: #45a049;
}

result {
		-moz-transition:background .1s ease-in;
		-o-transition:background .1s ease-in;
		-webkit-transition:background .1s ease-in;
		font-family: 'Roboto', sans-serif;
		width: 55%;
		font-size: 16;
		display: inline-flex;
		background:linear-gradient(to right, #f2f2f2 85%, maroon 15%);
		color: black;
		padding: 14px 20px;
		margin: 4px 0;
		border: none;
		border-radius: 40px;
		text-align: left;
}
result:hover {
		-moz-transition:background .1s ease-in;
		-o-transition:background .1s ease-in;
		-webkit-transition:background .1s ease-in;
		cursor: pointer;
		background:linear-gradient(to right, #e2ffde 82%, maroon 18%);
}
number {
		font-family: 'Roboto', sans-serif;
		font-size:26;
		padding: 12px 1px;
		position:absolute;
		left: 73.375%;
		cursor: pointer;
		color: white;
}

@media only screen and (max-width: 768px) {
  /* For mobile phones: */
	input[type=text], select {
			width: 80%;
			padding: 12px 20px;
			margin: 4px 0;
			  display: inline-block;
			border: 1px solid #ccc;
			border-radius: 40px;
			box-sizing: border-box;
	}
	result {
		-moz-transition:background .1s ease-in;
		-o-transition:background .1s ease-in;
		-webkit-transition:background .1s ease-in;
		font-family: 'Roboto', sans-serif;
		width: 80%;
		font-size: 16;
		display: inline-flex;
		background:linear-gradient(to right, #f2f2f2 85%, maroon 15%);
		color: black;
		padding: 14px 20px;
		margin: 4px 0;
		border: none;
		border-radius: 40px;
		text-align: left;
	}
	number {
		font-family: 'Roboto', sans-serif;
		font-size:26;
		padding: 12px 6px;
		position:absolute;
		left: 82.375%;
		cursor: pointer;
		color: white;
	}
	h1 {
		font-size: 28;
		font-family: 'Dosis', sans-serif;
		text-align: center;
	}
}


		
</style>
</head>
<body>

<div>&nbsp;</div>


<h1 id="title">Welcome to the Cookieville Bank!</h1>

<p class="sub">What would you like?</p>
    <p id="demo"> </p>
<div>
  <form>
    
    <input type="text" id="sbar" name="searchbar" placeholder="block/item" oninput="searchBar()">

    
    

    
    
  
<!--    <input type="submit" value="Submit"> -->
  </form>
</div>    
<div id="results">
</div>
    
<script>

var all = "Oak Wood,Spruce Wood,Birch Wood,Jungle Wood,Acacia Wood,Dark Oak Wood,Mangrove Wood,Warped Hyphae,Crimson Hyphae,#,#,#,#,#,#,#,Oak Log,Spruce Log,Birch Log,Jungle Log,Acacia Log,Dark Oak Log,Mangrove Log,Warped Stem,Crimson Stem,#,#,#,#,#,#,#,Oak Planks,Spruce Planks,Birch Planks,Jungle Planks,Acacia Planks,Dark Oak Planks,Mangrove Planks,Warped Planks,Crimson Planks,#,#,#,#,#,#,#,Oak Slab,Spruce Slab,Birch Slab,Jungle Slab,Acacia Slab,Dark Oak Slab,Mangrove Slab,Warped Slab,Crimson Slab,#,#,#,#,#,#,#,Oak Stairs,Spruce Stairs,Birch Stairs,Jungle Stairs,Acacia Stairs,Dark Oak Stairs,Mangrove Stairs,Warped Stairs,Crimson Stairs,#,#,#,#,#,#,#,Oak Sapling,Spruce Sapling,Birch Sapling,Jungle Sapling,Acacia Sapling,Dark Oak Sapling,Mangrove Propagule,Warped Fungus,Crimson Fungus,#,#,#,#,#,#,#,Oak Door,Spruce Door,Birch Door,Jungle Door,Acacia Door,Dark Oak Door,Mangrove Door,Warped Door,Crimson Door,#,#,#,#,#,#,#,Stripped Oak Log,Stripped Spruce Log,Stripped Birch Log,Stripped Jungle Log,Stripped Acacia Log,Stripped Dark Oak Log,Stripped Mangrove Log,Stripped Warped Stem,Stripped Crimson Stem,#,#,#,#,#,#,#,Stripped Oak Wood,Stripped Spruce Wood,Stripped Birch Wood,Stripped Jungle Wood,Stripped Acacia Wood,Stripped Dark Oak Wood,Stripped Mangrove Wood,Stripped Warped Hyphae,Stripped Crimson Hyphae,#,#,#,#,#,#,#,Oak Leaves,Spruce Leaves,Birch Leaves,Jungle Leaves,Acacia Leaves,Dark Oak Leaves,Mangrove Leaves,Azalea Leaves,Flowering Azalea Leaves,#,#,#,#,#,#,#,Oak Sign,Spruce Sign,Birch Sign,Acacia Sign,Jungle Sign,Dark Oak Sign,Mangrove Sign,Warped Sign,Crimson Sign,#,#,#,#,#,#,#,Stone Pressure Plate,Oak Pressure Plate,Spruce Pressure Plate,Birch Pressure Plate,Jungle Pressure Plate,Acacia Pressure Plate,Dark Oak Pressure Plate,Mangrove Pressure Plate,Warped Pressure Plate,Crimson Pressure Plate,#,#,#,#,#,#,Stone Button,Oak Button,Spruce Button,Birch Button,Jungle Button,Acacia Button,Dark Oak Button,Mangrove Button,Warped Button,Crimson Button,#,#,#,#,#,#,Oak Fence,Spruce Fence,Birch Fence,Jungle Fence,Acacia Fence,Dark Oak Fence,Mangrove Fence,Warped Fence,Crimson Fence,#,#,#,#,#,#,#,Oak Fence Gate,Spruce Fence Gate,Birch Fence Gate,Jungle Fence Gate,Acacia Fence Gate,Dark Oak Fence Gate,Mangrove Fence Gate,Warped Fence Gate,Crimson Fence Gate,#,#,#,#,#,#,#,Oak Trapdoor,Spruce Trapdoor,Birch Trapdoor,Jungle Trapdoor,Acacia Trapdoor,Dark Oak Trapdoor,Mangrove Trapdoor,Warped Trapdoor,Crimson Trapdoor,#,#,#,#,#,#,#,Ochre Froglight,Verdant Froglight,Pearlescent Froglight,Shroomlight,Mycelium,Rooted Dirt,Spore Blossom,Hanging Roots,Glow Lichen,Lily Pad,Cactus,Mud,Packed Mud,Mud Bricks,Mangrove Roots,Muddy Mangrove Roots,Mud Brick Slab,Mud Brick Stairs,Mud Brick Wall,Brick Slab,Brick Stairs,Brick Wall,End Stone,End Stone Bricks,End Stone Brick Slab,End Stone Brick Stairs,End Stone Brick Wall,Purpur Block,Purpur Pillar,Purpur Slab,Purpur Stairs,Petrified Oak Slab,Brick,Bricks,Clay,Clay Ball,Cobweb,Vines,Tuff,Moss Carpet,Moss Block,Shulker Shell,Respawn Anchor,End Rod,End Crystal,Ender Chest,Ender Pearl,Eye of Ender,Granite,Granite Slab,Granite Stairs,Granite Wall,Polished Granite,Polished Granite Slab,Polished Granite Stairs,Diorite,Diorite Slab,Diorite Stairs,Diorite Wall,Polished Diorite,Polished Diorite Slab,Polished Diorite Stairs,Smooth Stone,Smooth Stone Slab,Stone,Stone Slab,Stone Stairs,Andesite,Andesite Slab,Andesite Stairs,Andesite Wall,Polished Andesite,Polished Andesite Slab,Polished Andesite Stairs,Stone Bricks,Stone Brick Slab,Stone Brick Stairs,Stone Brick Wall,Cracked Stone Bricks,Chiseled Stone Bricks,Mossy Stone Bricks,Mossy Stone Brick Slab,Mossy Stone Brick Stairs,Mossy Stone Brick Wall,Cobblestone Slab,Cobblestone Stairs,Cobblestone Wall,Mossy Cobblestone,Mossy Cobblestone Slab,Mossy Cobblestone Stairs,Mossy Cobblestone Wall,Red Sand,Red Sandstone,Red Sandstone Slab,Red Sandstone Stairs,Red Sandstone Wall,Prismarine,Prismarine Slab,Prismarine Stairs,Prismarine Wall,Prismarine Bricks,Prismarine Brick Slab,Prismarine Brick Stairs,Dark Prismarine,Dark Prismarine Slab,Dark Prismarine Stairs,Prismarine Shard,Prismarine Crystals,Sandstone,Sandstone Slab,Sandstone Stairs,Sandstone Wall,Chiseled Sandstone,Cut Sandstone,Cut Sandstone Slab,Smooth Sandstone,Smooth Sandstone Slab,Smooth Sandstone Stairs,Chiseled Red Sandstone,Cut Red Sandstone,Cut Red Sandstone Slab,Smooth Red Sandstone,Smooth Red Sandstone Slab,Smooth Red Sandstone Stairs,Iron Door,Iron Trapdoor,#,#,Blackstone,Blackstone Slab,Blackstone Stairs,Blackstone Wall,Polished Blackstone Bricks,Polished Blackstone Brick Slab,Polished Blackstone Brick Stairs,Polished Blackstone Brick Wall,Polished Blackstone Button,Polished Blackstone Pressure Plate,Chiseled Polished Blackstone,Cracked Polished Blackstone Bricks,Polished Blackstone,Polished Blackstone Wall,Polished Blackstone Slab,Polished Blackstone Stairs,Deepslate,Chiseled Deepslate,Polished Deepslate,Polished Deepslate Slab,Polished Deepslate Stairs,Polished Deepslate Wall,Deepslate Bricks,Deepslate Brick Slab,Deepslate Brick Stairs,Deepslate Brick Wall,Deepslate Tiles,Deepslate Tile Slab,Deepslate Tile Stairs,Deepslate Tile Wall,Cracked Deepslate Bricks,Cracked Deepslate Tiles,Cobbled Deepslate,Cobbled Deepslate Slab,Cobbled Deepslate Stairs,Cobbled Deepslate Wall,Gilded Blackstone,Light Weighted Pressure Plate,Heavy Weighted Pressure Plate,Nether Wart Block,Warped Wart Block,Warped Nylium,Crimson Nylium,Crimson Roots,Warped Roots,Nether Sprouts,Weeping Vines,Twisting Vines,Nether Brick,Nether Bricks,Nether Brick Slab,Nether Brick Stairs,Nether Brick Wall,Nether Brick Fence,Cracked Nether Bricks,Chiseled Nether Bricks,Red Nether Bricks,Red Nether Brick Slab,Red Nether Brick Stairs,Red Nether Brick Wall,Basalt,Polished Basalt,Smooth Basalt,Quartz Bricks,Block of Quartz,Quartz Slab,Smooth Quartz Block,Smooth Quartz Slab,Smooth Quartz Stairs,Chiseled Quartz Block,Quartz Pillar,Quartz Stairs,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,Bone,Bone Meal,Bone Block,Ink Sac,Glow Ink Sac,Item Frame,Glow Item Frame,Cocoa Beans,Lapis Lazuli,Block of Lapis Lazuli,Tinted Glass,Glass,Glass Pane,Terracotta,Candle,#,Red Dye,Green Dye,Purple Dye,Cyan Dye,Light Gray Dye,Gray Dye,Pink Dye,Lime Dye,Yellow Dye,Light Blue Dye,Magenta Dye,Orange Dye,Blue Dye,Black Dye,Brown Dye,White Dye,White Stained Glass,Orange Stained Glass,Magenta Stained Glass,Light Blue Stained Glass,Yellow Stained Glass,Lime Stained Glass,Pink Stained Glass,Gray Stained Glass,Light Gray Stained Glass,Cyan Stained Glass,Purple Stained Glass,Blue Stained Glass,Brown Stained Glass,Green Stained Glass,Red Stained Glass,Black Stained Glass,White Stained Glass Pane,Orange Stained Glass Pane,Magenta Stained Glass Pane,Light Blue Stained Glass Pane,Yellow Stained Glass Pane,Lime Stained Glass Pane,Pink Stained Glass Pane,Gray Stained Glass Pane,Light Gray Stained Glass Pane,Cyan Stained Glass Pane,Purple Stained Glass Pane,Blue Stained Glass Pane,Brown Stained Glass Pane,Green Stained Glass Pane,Red Stained Glass Pane,Black Stained Glass Pane,White Terracotta,Orange Terracotta,Magenta Terracotta,Light Blue Terracotta,Yellow Terracotta,Lime Terracotta,Pink Terracotta,Gray Terracotta,Light Gray Terracotta,Cyan Terracotta,Purple Terracotta,Blue Terracotta,Brown Terracotta,Green Terracotta,Red Terracotta,Black Terracotta,White Glazed Terracotta,Orange Glazed Terracotta,Magenta Glazed Terracotta,Light Blue Glazed Terracotta,Yellow Glazed Terracotta,Lime Glazed Terracotta,Pink Glazed Terracotta,Gray Glazed Terracotta,Light Gray Glazed Terracotta,Cyan Glazed Terracotta,Purple Glazed Terracotta,Blue Glazed Terracotta,Brown Glazed Terracotta,Green Glazed Terracotta,Red Glazed Terracotta,Black Glazed Terracotta,Black Concrete,Red Concrete,Green Concrete,Brown Concrete,Blue Concrete,Purple Concrete,Cyan Concrete,Light Gray Concrete,Gray Concrete,Pink Concrete,Lime Concrete,Yellow Concrete,Light Blue Concrete,Magenta Concrete,Orange Concrete,White Concrete,Black Concrete Powder,Red Concrete Powder,Green Concrete Powder,Brown Concrete Powder,Blue Concrete Powder,Purple Concrete Powder,Cyan Concrete Powder,Light Gray Concrete Powder,Gray Concrete Powder,Pink Concrete Powder,Lime Concrete Powder,Yellow Concrete Powder,Light Blue Concrete Powder,Magenta Concrete Powder,Orange Concrete Powder,White Concrete Powder,White Wool,Orange Wool,Magenta Wool,Light Blue Wool,Yellow Wool,Lime Wool,Pink Wool,Gray Wool,Light Gray Wool,Cyan Wool,Purple Wool,Blue Wool,Brown Wool,Green Wool,Red Wool,Black Wool,White Carpet,Orange Carpet,Magenta Carpet,Light Blue Carpet,Yellow Carpet,Lime Carpet,Pink Carpet,Gray Carpet,Light Gray Carpet,Cyan Carpet,Purple Carpet,Blue Carpet,Brown Carpet,Green Carpet,Red Carpet,Black Carpet,White Candle,Orange Candle,Magenta Candle,Light Blue Candle,Yellow Candle,Lime Candle,Pink Candle,Gray Candle,Light Gray Candle,Cyan Candle,Purple Candle,Blue Candle,Brown Candle,Green Candle,Red Candle,Black Candle,Block of Copper,Exposed Copper,Weathered Copper,Oxidized Copper,Cut Copper,Exposed Cut Copper,Weathered Cut Copper,Oxidized Cut Copper,Cut Copper Stairs,Exposed Cut Copper Stairs,Weathered Cut Copper Stairs,Oxidized Cut Copper Stairs,Cut Copper Slab,Exposed Cut Copper Slab,Weathered Cut Copper Slab,Oxidized Cut Copper Slab,Waxed Block of Copper,Waxed Exposed Copper,Waxed Weathered Copper,Waxed Oxidized Copper,Waxed Cut Copper,Waxed Exposed Cut Copper,Waxed Weathered Cut Copper,Waxed Oxidized Cut Copper,Waxed Cut Copper Stairs,Waxed Exposed Cut Copper Stairs,Waxed Weathered Cut Copper Stairs,Waxed Oxidized Cut Copper Stairs,Waxed Cut Copper Slab,Waxed Exposed Cut Copper Slab,Waxed Weathered Cut Copper Slab,Waxed Oxidized Cut Copper Slab,Iron Ore,Deepslate Iron Ore,Coal Ore,Deepslate Coal Ore,Copper Ore,Deepslate Copper Ore,Diamond Ore,Deepslate Diamond Ore,Redstone Ore,Deepslate Redstone Ore,Lapis Lazuli Ore,Deepslate Lapis Lazuli Ore,Emerald Ore,Deepslate Emerald Ore,Gold Ore,Deepslate Gold Ore,Raw Copper,Raw Gold,Raw Iron,Block of Raw Copper,Block of Raw Gold,Block of Raw Iron,Block of Gold,Block of Iron,Copper Ingot,Gold Ingot,Iron Ingot,Gold Nugget,Iron Nugget,Iron Bars,Chain,Bucket,Arrow,Spectral Arrow,Feather,Stick,Flint,Coal,Charcoal,Block of Coal,Block of Diamond,Block of Emerald,Diamond,Emerald,Amethyst Shard,Spyglass,Block of Amethyst,Calcite,Rail,Powered Rail,Activator Rail,Detector Rail,Lever,Redstone Torch,Redstone Dust,Redstone Repeater,Redstone Comparator,Redstone Lamp,Block of Redstone,Tripwire Hook,Daylight Detector,Note Block,Jukebox,Target,Slimeball,Slime Block,Piston,Sticky Piston,Chest,Trapped Chest,Lightning Rod,Dispenser,Dropper,Hopper,Observer,Anvil,Chipped Anvil,Damaged Anvil,Compass,Recovery Compass,Loom,Composter,Barrel,Smoker,Blast Furnace,Cartography Table,Fletching Table,Smithing Table,Grindstone,Lectern,Stonecutter,Bell,Crafting Table,Furnace,Cauldron,Enchantment Table,Honey Block,Honeycomb Block,Honeycomb,Honey Bottle,Glass Bottle,Bottle o' Enchanting,Brewing Stand,Blaze Rod,Ghast Tear,Nether Wart,Spider Eye,Fermented Spider Eye,Blaze Powder,Magma Cream,Glistering Melon Slice,Rotten Flesh,Torch,Soul Torch,Lantern,Soul Lantern,Campfire,Soul Campfire,Glowstone,Glowstone Dust,Soul Soil,Soul Sand,Magma Block,Obsidian,Crying Obsidian,Nether Gold Ore,Nether Quartz Ore,Nether Quartz,Tube Coral Block,Brain Coral Block,Bubble Coral Block,Fire Coral Block,Horn Coral Block,Tube Coral,Brain Coral,Bubble Coral,Fire Coral,Horn Coral,Tube Coral Fan,Brain Coral Fan,Bubble Coral Fan,Fire Coral Fan,Horn Coral Fan,Pointed Dripstone,Dead Tube Coral Block,Dead Brain Coral Block,Dead Bubble Coral Block,Dead Fire Coral Block,Dead Horn Coral Block,Dead Tube Coral,Dead Brain Coral,Dead Bubble Coral,Dead Fire Coral,Dead Horn Coral,Dead Tube Coral Fan,Dead Brain Coral Fan,Dead Bubble Coral Fan,Dead Fire Coral Fan,Dead Horn Coral Fan,Dripstone Block,Sea Lantern,Echo Shard,Sponge,Wet Sponge,Kelp,Dried Kelp Block,Dried Kelp,Seagrass,Sea Pickle,Scute,Turtle Shell,Phantom Membrane,Conduit,Nautilus Shell,Heart of the Sea,Flower Pot,Dandelion,Poppy,Blue Orchid,Allium,Azure Bluet,Red Tulip,Orange Tulip,White Tulip,Pink Tulip,Oxeye Daisy,Cornflower,Lily of the Valley,Sunflower,Lilac,Rose Bush,Peony,Wither Rose,Azalea,Flowering Azalea,Coarse Dirt,Podzol,Dirt Path,Grass Block,Grass,Fern,Brown Mushroom,Red Mushroom,Brown Mushroom Block,Red Mushroom Block,Mushroom Stem,Big Dripleaf,Small Dripleaf,Dead Bush,TNT,Gunpowder,Paper,Book,Bookshelf,Leather,Painting,Melon,Melon Seeds,Melon Slice,Pumpkin,Carved Pumpkin,Jack o'Lantern,Pumpkin Seeds,Pumpkin Pie,Raw Porkchop,Cooked Porkchop,Raw Chicken,Cooked Chicken,Raw Mutton,Cooked Mutton,Raw Beef,Steak,Raw Rabbit,Cooked Rabbit,Raw Cod,Cooked Cod,Raw Salmon,Cooked Salmon,Pufferfish,Tropical Fish,Hay Bale,Wheat,Bread,Wheat Seeds,Egg,Sugar Cane,Sugar,Cake,Golden Apple,Apple,Cookie,Glow Berries,Sweet Berries,Rabbit Stew,Rabbit's Foot,Rabbit Hide,Beetroot,Beetroot Seeds,Beetroot Soup,Carrot,Golden Carrot,Potato,Baked Potato,Poisonous Potato,Sculk Sensor,Sculk,Sculk Catalyst,Sculk Shrieker,Sculk Vein,Chorus Fruit,Popped Chorus Fruit,Chorus Flower,Name Tag,Bamboo,Scaffolding,Ladder,Bowl,String,Clock,Ice,Frosted Ice,Packed Ice,Blue Ice,Snow Block,Snowball,Lead,Fire Charge,Armor Stand,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#,#"
  
var allthings = all.split(",");

const carpets = ["Red","Green","Purple","Cyan","Light Gray","Gray","Pink","Lime","Yellow","Light Blue","Magenta","Orange","Blue","Black","Brown","White"];
const colors = ["#b02e26","#5d7c15","#8932b7","#169c9d","#9c9d97","#474f52","#f38caa","#80c71f","#ffd83d","#3ab3da","#c64fbd","#f9801d","#3c44a9","#1d1c21","#825432","#f7fcfc"];
const numberstrings = ["1st","2nd","3rd","4th","5th","6th","7th","8th"];

var x = "";
var query = x;

function searchBar()
{
	x = document.getElementById("sbar").value;
	
	query = x.toLowerCase();
	document.getElementById("results").innerHTML = "";
	if(x != "" && !x.includes("#") && x.length >= 1)
	{
	allthings.forEach(locate);
	}
	

  
	var customIndexOf = function(array, searchElement, fromIndex)
	{
		if(!x.includes("#"))
		{
			return array.map(function(value)
			{
				return value.toLowerCase();
			}).indexOf(searchElement.toLowerCase(), fromIndex);
		}
		else
		{
			return -1;
		}
	};
	
	var output = customIndexOf(allthings, x);
	
	
	
	
	
/*	
	if(output != -1)
	{
	var countinfloor = output-(256*Math.floor(4*(output/1024)));
	var countinsegment = countinfloor - 16*Math.floor(countinfloor/16);
	var side = "left"
	if(countinsegment >= 8)
	{
		countinsegment = 15-countinsegment;
		side = "right";
	}	
	document.getElementById("demo").innerHTML = allthings[output] + " can be found on floor " + ((Math.ceil(4*((output+1)/1024)) + 9).toString(36).toUpperCase()) + ".<br>Please follow the " + carpets[(Math.floor((countinfloor)/16))] + " Carpet.<br>It is the " + numberstrings[countinsegment] + " from the " + side + ".";
	}
	
	*/

}

function locate(item, index)
{
	if(item.toLowerCase().includes(query))
	{
		const para = document.createElement("result");
		const node = document.createTextNode(item);
		para.appendChild(node);
		const element = document.getElementById("results");
		element.appendChild(para);
		var countinfloor = index-(256*Math.floor(4*(index/1024)));
		var countinsegment = countinfloor - 16*Math.floor(countinfloor/16);
		var side = "left"
		if(countinsegment >= 8)
		{
			countinsegment = 15-countinsegment;
			side = "right";
		}
		var colortouse = (Math.floor((countinfloor)/16));

		para.style.background =	"linear-gradient(to right, #f2f2f2 85%, " + colors[colortouse] + " 15%)";
		
		
		const para2 = document.createElement("number");
		const node2 = document.createTextNode(((Math.ceil(4*((index+1)/1024)) + 9).toString(36).toUpperCase()));
		para2.appendChild(node2);
		const element2 = document.getElementById("results");
		element2.appendChild(para2);
		if(carpets[colortouse] == "White")
		{
			para2.style.color = "black";
		}
		
		
		
		// <number style="font-size:26; padding: 12px 1px; position:absolute; left: 73.375%; cursor: pointer; color: white;">A</number>
		
		
		
		

//		document.getElementById("demo").innerHTML = allthings[index] + " can be found on floor " + ((Math.ceil(4*((index+1)/1024)) + 9).toString(36).toUpperCase()) + ".<br>Please follow the " + carpets[(Math.floor((countinfloor)/16))] + " Carpet.<br>It is the " + numberstrings[countinsegment] + " from the " + side + ".";
	}

}



</script>

<!--
<div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div><div>&nbsp;</div>
<p>by</p>
<p style="margin-top: -15px;">block facts</p>
-->


</body></html>