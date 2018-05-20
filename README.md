<p align="center">
  <img src="https://github.com/benchlab/benchx-media/raw/master/benos-logo.png" width="300px" alt="benOS Logo"/>
</p> <br>

# Designate
Decentralized Naming Service For Bench dApps, Networks, Wallets and Users.

## What Purpose Does Designate Serve?
Designate is very similar to DNS within the central internet. Where DNS correlates a domain name or TLD to a network address. Designate was designed with the same approach of correlation but works dramatically different and expands to help [Aero](https://github.com/benchlab/aero) as a decentralized content delivery network (CDN), by giving HRAs (Human-Readable Addressses) that correlate with network-based objects and network-based entities and their UID's (unique identifiers). This can help with the utilization and correlation of network-based objects and network-based entities by using HRAs, rather than long and hard to remember UIDs. Using HRAs for the retreival of network-based objects (videos, text-files, audio, images, folders, etc) makes life easier on developers and can be used by dApp and website developers who are looking to host on the Bench Network and also helps with the importing of Aero-based objects in their dApps and website code, without the need to write extra code and spend extra time developing their dApp, like it would on other networks that don't have `Decentralized Designation`. 

Although Designate is responsible for the registration of a HRA (Human-readable address) network address, it is not responsible for UID addresses that HRA's correlate to. [Kepler](https://github.com/benchlab/kepler) is responsible for deliving out UIDs to all kinds of network objects, dApps and other things floating across the Bench universe and is responsible for correlating where those objects actually exist or what that address points to. Designate simply points a HRA to a Kepler-based UID, so that's easy for users to remember and utilize, when exploring the Bench Network.

Bench's network has so many moving parts due to its components and its overall purpose. Below are a list of the components that Designate is designed to give human-readable names to access by pointing to their Kepler-based UIDs:

- `objects` - Objects on the Bench Network means videos, text-files, audio, images, folders, etc. <br>
-- `videos` - Video files uploaded to the network via benOS-based dApps.<br>
-- `text-files` - Text files uploaded to the network via benOS-based dApps.<br>
-- `audio` - Audio files uploaded to the network via benOS-based dApps.<br>
-- `image` - Image files uploaded to the network via benOS-based dApps.<br>
-- `folder` - Folder files uploaded to the network via benOS-based dApps.<br>

- `network entities` - Network entities on the Bench Network means networks, computers (nodes), dApps, websites, wallets and accounts. <br>
-- `networkId` - Networks all have a UID. Designate can give them a HRA. <br>
-- `nodeId` - Nodes are computers running benOS. Designate can give those computers HRAs.<br>
-- `dappId` - dApps are decentralized apps on the Bench Network. Designate can give them HRAs.<br>
-- `websiteAddr` - Websites can be hosted on the Bench Network. For easy access via [Telescope](https://github.com/benchlab/telescope), like web addresses of old, Designate can create HRAs for websites. <br>
-- `walletAddr` - Wallets are created via the benOS native dApp [BenchWallet](https://github.com/benchlab/benchwallet) and addresses from even remote networks, can be given an HRA. <br>
-- `accountId` - Every user on the network has a Kepler-generated `accountId`, Designate can give a HRA that correlates to this `accountId`<br>

## Designate-based HRAs for TLDs and File Extensions
Designate and Kepler work together, where Kepler hands out UIDs to everything on the Bench Network and Designate hands out HRAs that point to those UIDs. Designate creates the true `dWeb`, by creating a new TLD system that creates a registration system for decentralized domains that are utilized by websites within the Bench Network and HRAs for File Extensions for files located on the network. The only true downside to a decentralized operating system, is that naming files something other than their auto-generated UIDs, would be to register an HRA for the file. 

For example, lets say you have a picture of your mom and dad and Kepler gives it the UID of `AAAAC3NzaC1lZDI1NTE5AAAAIDEljglXMulz8404XwUBwbhZoWJmqWEH1IsQb9WN3.jpg` along with the image extension, correlated to the image-type of the image, in this case `.jpg`. You could create a HRA for this image through Designate like `picture-of-mom-and-dad.jpg`. The reason for having to do this, is because a decentralized operating system, doesn't store your files locally, while your local resources my store files of other users locally, you have no access to this data - as you shouldn't. Only the network does. Being that this is the case, there is no "Rename" functionality, when it relates to renaming the name of a file, since Kepler gives it a UID upon creation, so that it can find the location of that file wherever it is in the network. Using Designate, creating a HRA, as long as the HRA hasn't been taken - is possible. 

## Designate Custom TLDs and Extension Names
One of Designate's coolest features is that it gives users the ability to create their own TLDs and Extensions. Don't worry, there is no need to go to iCANN **lol**, custom TLDs and Extension Names can be created instantly and used by anyone at that point, using the Bench Network. To continue with our example from above, lets say you don't want to use the native `.jpg` HRA Extension Name, you could create `.yourname` so that you can create the filename `mom-dad.johndoe`. Even though .johndoe isn't an image file-type, the network realizes that `.johndoe` is a Designate-based HRA and is able to coorlate that to the base UID generated by Kepler at `AAAAC3NzaC1lZDI1NTE5AAAAIDEljglXMulz8404XwUBwbhZoWJmqWEH1IsQb9WN3.jpg`. This is because Designate is a decentralized naming service but also a decentralized domain name system (DDNS). 

## Designate-CLI
Just like [Kepler](https://github.com/benchlab/kepler), Designate also has it's own CLI, [Designate-CLI](https://github.com/benchlab/designate), used to claim HRAs through Bench Network's Designate service. Below are examples of how you can use Designate-CLI. 

### Designate-CLI Usage

#### Designate Kepler Account
You can easily `designate` an Account HRA by using the Kepler Account UUID Key, not to be confused with the `account_uuid`. The -d flag stands for `designate-name` and `nomoreheroes` in the example below would be the Account HRA being designated. 

```
# designate account 2fd305ea-912c-405b-bfed-7d98143d0d56 -d nomoreheroes
'nomoreheroes' is available and now designated as a premium name for 2fd305ea-912c-405b-bfed-7d98143d0d56
```

#### Designate Dig Designated Account Name 
You can easily `dig` the original Kepler account data that's related to a Designate Account HRA as is shown in the example below. 

```
# designate account dig -d nomoreheroes 

Displaying Kepler account information for designated namespace "nomoreheroes"
┌──────────────────────────────────────┬───────────────────────────────────────────────────────────────────────────┐
│             kepler uuid              │             account_uuid             │           wallet_addr              │
├──────────────────────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ 2fd305ea-912c-405b-bfed-7d98143d0d56 │ e4f48839-db29-47c4-abc9-7e33dada1858 │  ba9ce39273b2a1cf04cc948893fea3c8  │
└──────────────────────────────────────┴───────────────────────────────────────────────────────────────────────────┘
uuid: 2fd305ea-912c-405b-bfed-7d98143d0d56
account_uuid: e4f48839-db29-47c4-abc9-7e33dada1858
id: 3ebb0942f24e02c2f69d7d79bf4ace02645d42d247336738c0777084826aaac0
wallet_addr_uni: VYBioijzebrLwDX2K8wkMRLD98iRjbatQV4guXw2iDw=
wallet_addr_sec: upzjknOyoc8EzJSIk/6jyOGLIrS4mpml/hcQoMOaNDE=
uni_key: JGqZMWLzCx+1whWppWIHeCtmGf9VgP8EQ+j2/z3PZy4=
sec_key: ThO6DslXOwZucznK/E0jjUNYR3tw2sySjgW6HXjmd6wkapkxYvMLH7XCFamlYgd4K2YZ/1WA/wRD6Pb/Pc9nLg==
nonce: wcov83GTHsa4SPNABpgIO0Q2LmJVWoLK
hex_key: ba9ce39273b2a1cf04cc948893fea3c8e18b22b4b89a99a5fe1710a0c39a3431
klob: { 
uuid: 2fd305ea-912c-405b-bfed-7d98143d0d56,
account_uuid: 'e4f48839-db29-47c4-abc9-7e33dada1858',
time_created: '2018-05-20T07:11:22.526Z',
benchx_uuid: 'b33a4dcd-7057-4618-a635-9ad476cb45c3'
}
```

## What Is benOS
[benOS](https://github.com/benchlab/benos) is a decentralized operating system, originally based on Linux, uses some design strategies from [RedoxOS](https://github.com/redox-os) and even some design concepts from [OpenStack](https://github.com/openstack), [Ethereum](https://github.com/ethereum/go-ethereum) and [EOS](https://github.com/eosio). Although we utilize some of their design strategies, benOS is completely custom from a codebase perspective. 

benOS has many components that make the wheels turn. Below are a list of those components:

## Other benOS Network Components
[Nova](https://github.com/benchlab/nova) - Global Decentralized Hypervisor For The Bench Network <br>
[Kepler](https://github.com/benchlab/kepler) - Global Decentralized Identity Management For The Bench Network <br>
[Designate](https://github.com/benchlab/designate) - Global Decentralized Naming Service For The Bench Network <br>
[Flutter](https://github.com/benchlab/flutter) - Global Decentralized Image Service For The Bench Network <br>
[Neutron](https://github.com/benchlab/neutron) - Global Network Creation & Management For The Bench Network <br>
  - [BenchCore](https://github.com/benchlab/BenchCore) - Core Decentralized Network Component For The Bench Network <br>
  - [BenchChain](https://github.com/benchlab/BenchChain) - Neutron's RootChain On The Bench Network <br>

[Aero](https://github.com/benchlab/aero) - Global Object Storage Distributor & Manager For The Bench Network <br>
[Explorer](https://github.com/benchlab/explorer) - Global dApp Distributor, Manager and Viewer For The Bench Network <br>
[benFS](https://github.com/benchlab/benFS) - benOS FileSystem <br>
[dappJS](https://github.com/benchlab/dappjs) - dApp Development Kit For The Bench Network <br>
[Mercury](https://github.com/benchlab/mercury) - benOS Graphical User Interface <br>
[Asteroid](https://github.com/benchlab/go-asteroid) - benOS Native Programming Language <br>
[Meteor](https://github.com/benchlab/meteor) - benOS Native IDE for dApp Development <br>
<br><br>

## benOS Core Components
[benOS-Microkernel](https://github.com/benOS-Microkernel) - benOS Microkernel <br>
[benOS-Bootloader](https://github.com/benchlab/benOS-Bootloader) - benOS Bootloader <br>
[ParseArgs](https://github.com/benchlab/parseargs) - benOS-based Argument Parsing  <br>
[X](https://github.com/benchlab/X) - benOS Graphical User Interface <br>

**NOTE:** ***There are other pieces under development as well, as our development team grows.*** 

## CREDITS AND ATTRIBUTES
This portion of benOS may use software from other open source libraries. For a full list of software credits and acknowledgements, please visit [https://github.com/benchlab/benOS/blob/master/ATTRIBUTES.md](https://github.com/benchlab/benOS/blob/master/ATTRIBUTES.md).
The original LICENSE or LICENSES for the originating software(s) and library or libraries that were used to create `Designate` are still active, although, considering this Bench software and the softwares and/or libraries/packages it is `imported` into may be used to issue illegal securities, the BENCH LICENSE is activated for this purpose. This does not take away the credits, disable the originating LICENSE or in any way disown the original creation, creators, developers or organizations that originally developed many of the libaries used throughout Bench's large array of software libraries packaged together for the purposes of building a decentralized operating system (benOS)

## VERSION
0.1.0

## LICENSE
BENCH LICENSE<br>
For Designate
<br><br>
Copyright (c) 2018 Bench Computer, Inc. <legal@benchx.io>
<br><br>
Permission to use, copy, modify, and distribute this blockchain-related
software or blockchain-based software for any purpose with or without 
fee is hereby granted, provided that the above copyright notice and this 
permission notice appear in all copies.

THE USAGE OF THIS BLOCKCHAIN-RELATED OR BLOCKCHAIN-BASED SOFTWARE WITH THE
PURPOSE OF CREATING ICOS OR "INITIAL COIN OFFERINGS", UNREGISTERED SECURITIES 
SPECIFICALLY IN THE UNITED STATES OR IN OTHER COUNTRIES THAT HAVE A LEGAL 
FRAMEWORK FOR SECURITIES, IS PROHIBITED. BENCH FOUNDATION, LLC RESERVES THE 
RIGHT TO TAKE LEGAL ACTION AGAINST ANY AND ALL COMPANIES OR INDIVIDUALS WHO
USE THIS BLOCKCHAIN-RELATED OR BLOCKCHAIN-BASED SOFTWARE FOR THE PURPOSE OF 
DISTRIBUTING CRYPTOCURRENCIES WHERE THOSE CRYPTOCURRENCIES AND THEIR METHOD
OF DISTRIBUTION ARE IN DIRECT VIOLATION OF UNITED STATES SECURITIES LAWS. 
IF A GOVERNMENT BODY TAKES ACTION AGAINST ANY USERS, DEVELOPERS, MARKETERS,
ORGANIZATIONS, FOUNDATIONS OR ANY PROFESSIONAL ENTITY WHO CHOOSES TO UTILIZE
THIS SOFTWARE FOR THE DISTRIBUTION OF ILLEGAL SECURITIES, BENCH COMPUTER INC.
WILL NOT BE HELD LIABLE FOR ANY ACTIONS TAKEN BY THE USERS, DEVELOPERS, MARKETERS,
ORGANIZATIONS, FOUNDATIONS OR ANY PROFESSIONAL ENTITIES WHO CHOOSE TO DO SO.

UNITED STATES SECURITIES VIOLATIONS SPECIFICALLY REFER TO ANY VIOLATIONS OF
SECTION 10(b) OF THE SECURITIES EXCHANGE ACT OF 1934 [15 U.S.C. § 78j(b)] AND
RULE 10b-5(b) PROMULGATED THEREUNDER [17 C.F.R. § 240.10b-5(b)], AND
SECTIONS 5(a), 5(c), and 17(a)(2) OF THE SECURITIES ACT OF 1933 [15 U.S.C.
§§ 77e(a), 77e(c), and 77q(a)(2)]; BY MAKING USE OF ANY MEANS OR INSTRUMENTS
OF TRANSPORTATION OR COMMUNICATION IN INTERSTATE COMMERCE OR OF THE MAILS TO
SELL THROUGH THE USE OR MEDIUM OF ANY WRITTEN CONTRACT, OFFERING DOCUMENT,
PROSPECTUS, WHITEPAPER, OR OTHERWISE, ANY SECURITY AS TO WHICH NO REGISTRATION
STATEMENT WAS IN EFFECT. OR FOR THE PURPOSE OF SALE OR DELIVERY AFTER SALE,
CARRYING OR CAUSING TO BE CARRIED THROUGH THE MAILS OR IN INTERSTATE COMMERCE,
BY MEANS OR INSTRUMENTS OF TRANSPORTATION OR COMMUNICATION IN INTERSTATE
COMMERCE OR OF THE MAILS TO OFFER TO SELL OR OFFER TO BUY THROUGH THE USE OR 
MEDIUM OF ANY WRITTEN CONTRACT, OFFERING DOCUMENT, PROSPECTUS, WHITEPAPER,
OR OTHERWISE, SECURITIES AS TO WHICH NO REGISTRATION STATEMENT HAS BEEN FILED.

OUTSIDE OF THESE LEGAL REQUIREMENTS, THIS SOFTWARE IS PROVIDED "AS IS" AND 
THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING 
ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL 
THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL 
DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, 
WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, 
ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
