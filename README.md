# Vehicle Solar Installs

This is basically a brain-dump of what I've learned building-installing vehicle solar.


A few terms to know that I don't define lower:
* Shore Power - this is an external power source that you plug the vehicle into, such as a generator, RV hookup, or outlet in your garage. The term comes from power hookups for boats while docked.
* Starter Battery: This is the battery that's already in your car, it's mostly used to power your engine's starter motor when you turn on your car. It can provide a ton of current at once, but shouldn't be discharged very much so it isn't good for running accessories off of
* House Battery: This is the battery/batteries that you are going to charge with your solar and power various things with. The term comes from RVs
* Alternator: this is the thing attached to your car's engine that produces electricity while the car is running.
* Series/Parallel: these are two ways of wiring electrical things. [Wikipedia](https://en.wikipedia.org/wiki/Series_and_parallel_circuits). Most things we wire will effectively be in parallel, but it mostly comes up when talking about batteries and solar panels. Power sources wired in parallel add their amperage together, whereas power sources wired in series add their voltages together. Because we will use 12v batteries to power a 12v system, we will always wire our batteries in parallel, but depending on panels and charge controller there's a chance that wiring solar panels in series may make sense.
* Ground: this term is used sort of strangely in vehicle wiring. It isn't the same as a ground in building wiring - nothing in a car can be truly grounded given it's sitting on rubber tires. The "ground" in vehicle wiring is basically your negative circuit. All battery negative terminals will be connected to the vehicle's chassis, and the chassis is basically used as a giant built-in negative wire. So in this context "ground" ~= DC negative.

Abbreviations:
* A: Amps
* V: Volts
* W: Watts
* AH: Amp-Hours. This is how batteries are rated, for example a 12v 100AH battery could roughly power a 10A load for for 10 hours.
* WH: Watt-hours. This can also be used to measure battery capacity, and is better for comparing capacity across voltages. For example, 100 AH of 12V provides the same amount of power as 25AH of 48V.


# System Voltage
You almost certainly want a 12v system. For larger setups such as home solar or a large RV, 48v has a lot of advantages, but for an SUV it will just make your life complicated. Car electrical systems run on 12v, so it's easier to integrate a 12v system, and it's hard to get very small solar setups up to 48v. I don't think 24v systems are right for almost any use case.

# big-ticket items

## Required

### Solar Panels

#### panel types
The three panel types that are relevant here are rigid panels, flexible panels, and CIGS Panels.

##### Rigid Panels
Rigid panels are the cheapest, and usually come with an aluminum frame. A few relevant features that they may come with:
* n-type: these tend to be a bit more efficient (more power for a given area), but not really dramatically so. You may get ~10% more power.
* bifacial panels: these can make power on the backside as well, but for this to do much you need a gap behind it with a reflective surface. With good installation you may get ~10% more power. I don't think it's worth messing with for most vehicle installs. 

Rigid panels are best for flat surfaces such as the top of an RV, or for installing on top of rails such as some roof racks. You can expect to pay ~$0.90 / watt for quality panels in the 100-200w range.

##### Flexible panels
These are quite a bit thinner and lighter, and they have some flex to them. They can really only flex in one axis though, so they can't always follow vehicle contours the way you might want. You are theoretically still supposed to install these with an airflow gap behind them, but in practice nobody does that. These are best for flat-ish surfaces like roofs and hoods. I've found that even if they don't totally follow the contour of the surface, they don't catch enough air to be a problem. These are also easy to pack as portable panels because they are thin and light; a stack of them doesn't take up much space, but they are harder to set up at an optimal angle than panels with a frame so you will likely just lay them on the ground. You can expect to pay ~$1.15 / watt for these panels.

##### CIGS
These panels are even more flexible (they can follow compound curves) and are very durable. They are often put on the decks of boats where they get walked on. The main drawback is that they are very expensive, generally costing >$4/watt

Generally the first decision you need to make is whether you are going to mount solar panels on your vehicle or bring portable panels to set up when you are stopped.


#### Panel Sizing
Solar panels generally won't quite produce their full wattage rating even in perfect conditions, and perfect conditions are rare. Even days with bright sun are usually hot, and heat reduces panel efficiency. In a good environment (eg burning man), you will get ~5 hours * rated output on a sunny day, so you will get up to 500 watt-hours per day from a 100-watt panel.

The quantity of panels you need will be very specific to your use case - you may want extra solar and battery capacity to allow for cloudy days, or you can supplement with charging off of a generator, your car alternator while driving, or RV shore power hookups.

#### Vehicle Installation
This will vary quite a bit based on your vehicle; an RV with a big flat roof is quite a bit simpler than a smaller vehicle. Generally your location options are roof or hood. An SUV can fit 100-200w on the hood and ~300w if you dedicate the entire roof. Keep in mind that you may prefer to use the roof for storage than for solar panels. You can try to mount solar on top of your storage, but this can be complicated to waterproof and makes removing the storage more difficult.

Your general mounting options:
* Bolting to an existing rack: this works best for rigid panels. If you want to build your own mounting rack or frame, 4040 C-channel aluminum extrusions are a good strategy.

* Bolting to sheet metal: You are drilling holes in your car for this. This works well for flexible panels. The best way that I've found is using rivnuts and putting bolts into them, but you could also use normal rivets, self-tapping screws, or bolts with nuts on the back. Use washers and locking nuts or split washers.

* Adhesive: I don't really trust this, but some people have done this with success. The best option is VHT tape, which is commonly used for installing vehicle trim pieces. Make sure to clean the surface well before applying.

Getting wires into your vehicle can be difficult without drilling holes. Some vehicles have places you can do it, but there's not a general solution. If you do drill holes, you don't want to just run wiring through a sharp metal hole. To run into an area that doesn't need to be 100% watertight, such as your engine bay or a hole coming up from the floor of your vehicle, use rubber grommets. For something like a vehicle roof, you want to use a watertight "ingress gland" of appropriate size.

#### Portable Panels
These are handy if you don't want to drive around with panels on your car, or you want more solar than your vehicle has space for. Some companies make foldable panels for this purpose, or you can just grab some flexible panels that pack very flat. I have a folding 200w rigid panel that works well, but it is pretty heavy and I think I would be happier with something lighter. You can of course combine portable panels with installed panels; I have 100w installed on my vehicle and add a portable panel for trips where I will be parked for a long time.

#### brands
BougeRV and Renogy are the well-regarded brands with the most van/suv focused offerings. There are a lot

#### TODO: panel voltages and series/parallel ratings



### Battery
You will want a separate battery system from your vehicle starter battery. Starter batteries aren't appropriate for the workload, and you don't want to come back to a dead starter battery. You need to use "deep cycle" batteries that are designed to be deeply discharged.

You almost certainly want to use Lithium Iron Phosphate batteries (LiFePO4). They are the longest-lasting, safest, and require the least babysitting. A distant second place option is deep-cycle AGM batteries, but these last less long, have less capacity, and do not like being fully discharged. Do not use lithium-ion batteries; they can be dangerous, have a short lifespan, and need very specific charge/discharge patterns.

LiFePO4 batteries don't have thermal runaway problems like traditional lithium-ion batteries, and last much longer than other battery types, especially when being fully discharged. Most are rated for 10 years and thousands of discharge cycles.

You need to use 12v batteries. 12v batteries can be combined in series to make higher voltages, but higher voltage batteries cannot reasonably be used in 12v systems.

It's best to use chargers designed for LiFePO4 batteries. Other chargers can put charge into the batteries, but the best way to charge them involves topping them off with a higher-voltage "boost" period (~14.6v) but not keeping the voltage there.

### Capacity
The amount of capacity that you want is very dependent on your use case, but the smallest batteries that you should be considering are 100 amp-hours. You can combine multiple 12v batteries in parallel, including batteries of different capacities (although this is slightly less optimal than identical batteries.)

### Custom Batteries
It is possible to make custom batteries by buying individual cells and a management system. This is currently not actually any cheaper, but if you do it you want to buy prismatic grade A cells manufactured by EVE. It really only makes sense if you need to fit your battery into a weirdly-shaped space.

### Battery features
#### BMS (battery management system)
A BMS balances cell charges and provides protection features (eg high-temperature and high-power shutoff). Some very cheap batteries don't have a BMS and just wire the cells together. You don't want a battery without a BMS, but if for some reason you do use one it is extra-important to fuse it correctly.

#### low-temperature protection
LiFePO4 batteries will be damaged if they are charged at cold temperatures. This feature will prevent charging if the temperature is too low. If you don't have this feature, you need to have some other way of preventing charging if you go somewhere cold. This will usually be found on mid-priced batteries.

#### self heating
This is better than low temperature protection, and will direct charge current to a heater until the battery is warm enough to charge. This is only found on high-end batteries.

#### bluetooth
This allows you to get some battery information via your phone or sometimes a dedicated monitoring screen from the manufacturer. I don't think it's really necessary if you have a monitoring shunt, but it's nice to have. Bluetooth is a mid-price and up feature.

#### recommendations
I think the 230 AH low temp-protected battery from LiTime is a good price-performance sweet spot. LiTime is generally a mid-range brand with a good reputation. I know people who have been happy with cheaper batteries from Weize and Eco-Worthy. Renogy makes some of the better priced self heating options, and if I wanted to spend big money I'd probably buy from Epoch.

### Solar Charge Controller
Your solar charge controller needs to be rated for the voltage and amperage that your panels are producing, and needs to output 12v. Generally nicer chargers will be rated for higher voltages, which they can step down to 12v. This can let you run panels in series for higher voltages and thinner wires, but it's not really a big deal for small solar arrays. You want one designed to charge LiFePO4 batteries (most new ones are).

#### MPPT (Maximum Power Point Tracking)
This is the most relevant feature for solar charge controllers. It dynamically adjusts panel voltages to find what works best for current conditions and lets you get more power out of them.

#### Combined Units
Solar chargers can often be found combined with other things you might need, for example I use [this](https://www.renogy.com/dcc50s-12v-50a-dc-dc-on-board-battery-charger-with-mppt/) charger that is combined with a DC-DC charger designed for vehicle installations, and Victron's popular multiplus line combines a solar charger with an inverter, AC charger, and transfer switch.

### DC-DC charger
You will use this to charge your battery while the vehicle is running. You want one rated for 12v both in and out, and specifically designed for both LiFePO4i. In some cases you may be able to get by without solar at all if you are driving the vehicle for long periods of time and have enough battery to cover the periods in between (for example a multi-day road trip.)

It is important for the charger to shut off when the vehicle is not running. There are a few ways to accomplish this.

The most basic way is to wire it into an ignition-controlled circuit rather than directly to your starter battery terminal. This can be complicated and vehicle-specific, but it's likely that no ignition-controlled circuit with enough amperage is available, so you would need to use a high-current relay or contactor controlled by an ignition circuit but powered from the battery terminal.

Chargers designed for vehicles will have features to do this more simply. Most vehicles can use a system where the charger detects increased voltage from the alternator running (this will be ~13.5v with the alternator running and ~12.8v from the battery with the car off.) It is important to run the circuit from the battery with sufficient gauge wiring such that the voltage drop of the run doesn't prevent the charger from detecting the alternator.

Some very new vehicles have a "smart" alternator which will not always output a high voltage. These alternators will have a control line that indicates when they are running, and most new dc-dc chargers will have a terminal to wire this signal into.

Tesla-specific - I have been told that loads on tesla's 12v system can keep much of the car's electronics awake and drain the battery quickly, so you want charging to shut off with the ignition even on Tesla vehicles.

Some of the nicer chargers designed for vehicles have additional features such as topping off your starter battery from solar, or allowing you to charge the house battery from the starter battery while the vehicle is off until it reaches a certain state of discharge.

### Inverter
This will allow you to run electronics with standard AC wall plugs.

Some units have outlets directly on them, and some are designed to be hardwired into an outlet. You can also splice a power strip onto the hardwired ones. Many also have a remote switch, allowing you to turn them on and off if the inverter is located somewhere inconvenient.

The two main categories of inverter you will see are modified sine wave and pure sine wave. Pure sine wave converters are more expensive, but produce a more accurate AC waveform. Many devices will be unhappy with a modified sine waveform, for example it can burn out some types of electric motors more quickly. Modified sine wave inverters also often make a buzzing noise with certain loads.

You may or may not be concerned about idle power draw. Many inverters draw significant power even with no load (50 watts or more at idle). Some have a mode that allows them to mostly shut off and check whether a load is connected every few seconds to reduce idle power draw.

Most inverters have both a peak rating and a continuous rating - this matches the fact that many loads cause a high inrush current when starting up, but use less current once they are on. My experience has been that cheaper inverters can not actually hit their inrush rating, and you really need to size them based on matching your inrush to their continous load rating. In general things like laptop chargers have less inrush, while motors (and especially compressors for fridges/air conditioners) have very large inrush draws. Resistive loads such as anything with a heating coil have less inrush, but heaters and burners draw huge amounts of power continuously.

It is important to wire your inverters with sufficient gauge wire. They will usually be your largest power draw, and shut off if there is too much voltage drop. 

One major annoyance I've found with cheap inverters is that they may consider your charger's boost phase to be an overvoltage condition and beep and/or shut off.

Some inverters have built-in transfer switches. This will let you plug in to shore power and automatically switch the loads over. Some also have a built-in AC charger to also charge the battery from the same source.


## Optional

### AC Charger
This will allow you to plug your vehicle into shore power to charge the battery. I think the only ones that make sense are cheap small ones (~4 amp, I like my cheap one from NAPA) that you can leave plugged in long term when parked in a garage to keep things topped up, a fridge running, etc) or  pretty big ones (20 amp or more) that you can plug into a RV hookup or generator. Fully charging a relatively small (100AH) with a 20A charger will take over 5 hours, so smaller ones don't make much sense to me.

There are "inverter charger" options that combine AC chargers (usually 25+ amps) with inverters.

### DC Plug
If you want to plug in random things designed for car 12v sockets (phone chargers, fans, etc) then they probably use these cigarette lighter style plugs. They're really terrible plugs, but even if you hardwire everything or cut off all your plugs and replace them with something better you probably want to keep at least 1 around. Most of them are designed for mounting through a panel (maybe a box housing the rest of your electronics) but you can get free-hanging ones. Get one with a durable cover if you can.

### USB
There are 12v panel mount USB chargers available, or you can use "car chargers" plugged into lighter-style sockets. This will be more efficient than charging your phone through an inverter.

### Fridge
Not dealing with melted cooler water is pretty nice. The main decision here is 1 or 2 zone. Almost all of these can be set to any temperature and therefore act as a fridge or a freezer, but using a 2-zone you can have both a fridge and a freezer. I'm pretty happy with my IceCo 1-zone fridge. I don't see much point in the fancy fridges with built-in batteries; they can be removed from your car, but they're super heavy so why would you want to?

### Air Conditioner
Most of these mount on your roof, but there are "undermount" style options available for some vehicles. This does involve cutting a hole in your roof. Air conditioners draw a *ton* of power, so it may make sense to only run one when you are at an RV hookup

You can get these either powered by 12v DC or 110 AC. The 110 versions will be less efficient when running off of battery, but interact nicely with a transfer switch when plugged into shore power. 12V AC units will draw less power, but if you want to power them from shore power you need a high-power AC charger.


# Wiring

## Wire
You will need multiple sizes of wire. For DC wiring, I use 4, 8, and 12 gauge. Smaller wire is good for automotive sensors, but not power delivery.  I use TXL wire for most car stuff, but it's hard to find over 12 gauge. Look for automotive or marine "Primary Wire". I've heard of people using solid wire for smaller wires because it works well with wago nuts, but solid wire should not be used in vehicles - vibration and movement can make it work-harden and snap. "oxygen-free copper" is better than "copper-clad aluminum" but more expensive. If you use the aluminum stuff, consider going up a wire gauge or two. 

You can estimate the right size of wire to use with a chart like [this one](https://knowhow.napaonline.com/automotive-wiring-guide/). Note that a longer run requires a thicker wire for the same amount of current.

I like 14/3 marine wire for AC wiring; it will be sheathed together and use stranded conductors. Wire designed for installation in buildings will have solid conductors and should not be used.

It's important to understand that electrical wire is rated for current based on the conductor size, but rated for voltage based on the insulation. You need to use wire that is correctly rated for both your voltage and current. (There's also a temperature rating, but you shouldn't be running near your engine block or exhaust where this matters.)

## Connectors
I'll probably update this at some point with a long rant about how I hate most connectors, but here's my advice for people who don't want to buy lots of specialized tools: use XT60 connectors for most things, they are compact for their current rating and easy to come by. Get them with flying leads, because they suck to solder on. Most solar panels come with MC4 connectors, just use them for your external connections. They suck, but other sealed high-current options are expensive. Get decent heat shrink wire connectors,
I find [these wirefy ones](https://www.amazon.com/Wirefy-Heat-Shrink-Wire-Connectors/dp/B01GXQMP66/ref=sr_1_2_sspa?crid=31MLU4V0SMVBZ&dib=eyJ2IjoiMSJ9.uv_rZCyz5kxdB9iHPFRv2UC4DlGX1Ira1LX8Rb3OlisC0aYA1R4vIW9NBiHLFGJh922J22faVrwy7xJGhMSRAF5U1YLi5D4GufiXw0pPiz1eonSwMcWlH1v0gIboNZZTFUykKoKBkqCap3t4F37fwydjguUNN4M-9c1W9Hp6cJsPmSsEWfau9cGcz1mQi73pnkHYzKTguSTOr-dVJOrELYL5xhVowc9NJs6nPulAsx4.D0tvkf9iPyx7xr3JB5X83iNcwcDZWciYZk_bkV6zbuo&dib_tag=se&keywords=wirefy+butt+connectors&qid=1725582245&sprefix=wirefy%2Caps%2C211&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1) to be OK.
You can buy pre-terminated battery cables for short runs. If you don't want to buy a specialized crimper for longer large wires, you can buy premade welding cables but it may be hard to get the terminal sizes you need. 12ga is the largest you can use normal tools on, the cheap/normal connectors can go on 10ga but most basic wire strippers will only go up to 12ga on stranded wire.
[This crimper](https://www.amazon.com/AMZCNC-Operated-Hydraulic-Crimping-Electrical/dp/B097YCNN9D/ref=sr_1_1_sspa?crid=2O2SHL34ZSRR&dib=eyJ2IjoiMSJ9.YNgEc9jhioAUNz2YnfZ4IcdDk_tWG1jhPs0SNnwjfysNUbtHbzGzhE5eh58vnbmv24FvgHJeFz75dvKVmsFS6bc-GOLLs9akis2lnFfCri5Q7NLEe_kScJogStSOebELEYajQMAurpaeSf73rlNMNAvJGSgSb7MqxSqdsdbpguWPRJCLcEMEXOKyrZR7h96JJ0-Op52FJzVTGrg3AGwObg.qK2ZAuS9GmOHSQ6ZKo_14jeDdgDHJSbDuF0YaH7QzcQ&dib_tag=se&sprefix=hydraulic%2Bcrimpe%2Caps%2C167&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY) is pretty cheap and I've found it to work OK on bigger stuff (if you know me personally I can help with tools as well.)

## Circuit Protection
Circuits should be fused for ~20% over the expected draw of the circuit, but never greater than the wiring gauge is acceptable for. (It's probably fine to go a bit over the 3% drop the chart linked earlier is targeting, but it wouldn't be allowed in new car/boat construction.) Fusing should be done on the side *providing* the power. A fuse on the powered device isn't enough - that can protect the device, but it won't handle a short earlier in the circuit.

Some important concepts:
* amperage rating: the amperage at which the fuse/breaker blows/trips
* voltage rating: this is important because higher voltage takes a larger gap or insulator to interrupt
* interrupt rating: this is how high of an amperage of electrical arc the device can interrupt. When electricity is arcing, the air is turned into plasma, which conducts better than gaseous air. This means that once an arc has started, it is harder to interrupt and takes a larger gap than would have been required to prevent the arc from starting.
* AC vs DC: AC and DC interrupt devices sometimes have similar construction, but they are not the same. This is primarily because DC arcs are more difficult to interrupt; an AC arc can be interrupted during the neutral phase of the sine wave, but a DC arc has no such low voltage point so they are more difficult to interrupt. If you've only done AC wiring, you may not have heard of an interrupt rating because it is a less-important concept.
* time-current curve: good fuse manufacturers will have a data sheet for how long it will take to blow at a given current. The main thing to understand is that some fuses are designed to be "slow blow" and allow extra current for a while but blow before the wiring overheats, and other fuses are designed to be "fast blow" and blow quickly after the current rating is reached. Your main battery fuse should be slow-blow, sensitive electronics should be fast-blow, and other things are more negotiable.




### Fuses
Note that some fuse holders may be rated for less than the largest fuse you can physically put in them.
#### Blade Fuses
These are the most common type you see in cars, and are a good general-purpose option.

* Micro: These are nice due to the size, but fuse blocks for them are hard to find. Available up to 30A
* Mini: Available up to 30A
* Standard: (ATC/ATO, the only difference is whether the top exposes pins for a fuse tester). These are available up to 40A, but many fuse blocks are only rated for 30A. These are the most-commonly used fuses, this is probably what you think of when you think of a "fuse".
* Maxi (APX) These are available up to 100A, but there are few fuse block options.

#### stud-based fuses
These all look kind of similar and go between two posts. You will used them to protect higher-power circuits. Here are the maximum sizes you can get them in:

Mini ANL - up to 100A
ANL - up to a lot, 750A? These are the only fuses of this style with an interrupt rating high enough to be your primary battery fuse.

Midi - up to 200A
Mega - up to 300A

I have found the most products for ANL and Mini ANL, but for some reason many equipment vendors send you Mega fuses.

#### MRBTF (Marine-Rated Battery Terminal Fuses)
These are compact fuses designed to be your primary battery fuse. Most holders for them are designed to sit directly on your terminal studs. They are very compact for their capacity, but there aren't many fuse holder options for them.


#### recommendations
Consider MRBTF for your main battery fuse, mini ANL for most big circuits, and regular ATC for smaller stuff.

### Breakers
I haven't found any DC breakers that I really like, but here are your options:

#### Cheap thermal fuses
[This style](https://www.amazon.com/Blue-Sea-Systems-Circuit-Breakers/dp/B004XXOW0E/ref=sr_1_14_sspa?crid=35YX8GDBOZQS&dib=eyJ2IjoiMSJ9.F-7xHl_2UGtbrkXkLI8JjgZAtMJKGdvTqhRvzffxSmJ570jyOTRM1mkV49jbY9MfkxnY-7c7wUMM1NF06zdasElEOyoOAdqH8wecWAAGm7CpM_B_PPN5fLSo4QPUwENuSjGgQyJitABTGA2AFBZV2CQ7CpXclQB7gPkf5K8ULVV7JHYj5AsSHj8q_QsZrgTzROWit8YSOjU1Edw3nSHKtP06xa8Q6UIa4Fjph8u_4NEPnA3PYAwsndh5UjH29ZcocwCmTI6-M96HqlZ6cdRK4124H2RWghw5WbPu1bv2ons.booQ1fehdJqRo8Ek_CJy8xBL94SVDRubzQvSDEoMydg&dib_tag=se&keywords=dc%2Bthermal%2Bfuse%2B60a&qid=1725580649&sprefix=dc%2Bthermal%2Bfuse%2B60a%2Caps%2C201&sr=8-14-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9tdGY&th=1) 
Seems to be OK and the ability to use as a switch is nice.

[this style](https://www.amazon.com/ANJOSHI-Holders-Overload-Protection-Inverter/dp/B07CXTVXJD/ref=sr_1_21?crid=35YX8GDBOZQS&dib=eyJ2IjoiMSJ9.F-7xHl_2UGtbrkXkLI8JjgZAtMJKGdvTqhRvzffxSmJ570jyOTRM1mkV49jbY9MfkxnY-7c7wUMM1NF06zdasElEOyoOAdqH8wecWAAGm7CpM_B_PPN5fLSo4QPUwENuSjGgQyJitABTGA2AFBZV2CQ7CpXclQB7gPkf5K8ULVV7JHYj5AsSHj8q_QsZrgTzROWit8YSOjU1Edw3nSHKtP06xa8Q6UIa4Fjph8u_4NEPnA3PYAwsndh5UjH29ZcocwCmTI6-M96HqlZ6cdRK4124H2RWghw5WbPu1bv2ons.booQ1fehdJqRo8Ek_CJy8xBL94SVDRubzQvSDEoMydg&dib_tag=se&keywords=dc%2Bthermal%2Bfuse%2B60a&qid=1725580649&sprefix=dc%2Bthermal%2Bfuse%2B60a%2Caps%2C201&sr=8-21&th=1) seems to have fewer reputable sources, and I've had them trip well before their rated amperage.

### DC Mini Circuit Breakers (sometimes called "DC MCB")
These look more similar to the AC breakers you're used to seeing in your house. Many of them are designed to mount on a DIN rail, but they often come with a little DIN rail to put them on.

The important thing to understand with these is that they are directional. They use a magnet to pull electrical arcs into an insulator, but in the wrong direction the arc will be pushed away from the insulator. They are a nice form factor but shouldn't be used anywhere you might get a backfeed surge. I'm not a EE and know that diodes can burn out and make current flow in weird directions, so I avoid these.


### Brands
You can't trust random amazon stuff to actually meet it's rating. If you use it, consider adding some safety margin. For fuses and breakers, I would get stuff from reliable sources such as Blue Sea and Bussman.

## low voltage cutoff
You may find it useful to be able to cut off most circuits at a certain battery level, for example to keep a fridge running. There are some cheap options available on Amazon, but here are some considerations:

* Some have a programable level, but some do not. The non-programmable ones are often set to 10V, which for a 12V battery is completely dead. This is not useful. Some of the non-programmable ones can actually be taken apart and have potentiometers you can use to adjust the voltage, even though they don't advertise this.

* They have fairly low current limits, and you may want to pass large loads from them. Most of them are also explicitly not protected from backfeed, so they shouldn't be used to run an inverter directly. I recommend getting a low-current one and using it to control a high-current relay.


TODO: battery + wiring boxes. The easiest thing to do is mount everything on a little piece of plywood.
