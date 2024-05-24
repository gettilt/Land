<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Land
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Land is shrinking in the world, yet it is the only hard asset that has any value, protected from inflation and regulation. Any companies that own land will win.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| ADC | Agree Realty Corporation focuses on the acquisition and development of properties leased to retailers, indirectly benefiting from land ownership through its retail locations. | chat_gpt,google |
| AMT | American Tower Corporation owns and operates cell towers, indirectly benefiting from land ownership through leasing sites. | chat_gpt,claude,google |
| BAM | Brookfield Asset Management invests in real assets, including real estate and infrastructure, indirectly benefiting from land ownership. | chat_gpt |
| CBRE | CBRE Group, Inc. provides real estate services and invests in real estate, indirectly benefiting from the value of land through its services. | chat_gpt |
| CCI | Crown Castle owns, operates, and leases more than 40,000 cell towers and approximately 80,000 route miles of fiber supporting small cells and fiber solutions, indirectly benefiting from land ownership. | chat_gpt,claude,google |
| FPI | Farmland Partners Inc. owns and aims to acquire high-quality farmland throughout North America, benefiting directly from the value of owning land. | chat_gpt,google |
| FR | First Industrial Realty Trust, Inc. owns and operates industrial real estate, benefiting from land ownership in key logistic locations. | chat_gpt |
| LAND | Gladstone Land Corporation focuses on owning farmland, leasing it to farmers, and benefiting from the appreciation of land value. | chat_gpt,claude,google |
| PCH | PotlatchDeltic Corporation is involved in timberland management and real estate sales, directly benefiting from land ownership. | chat_gpt,claude,google |
| PLD | Prologis, Inc. is a leader in logistics real estate, owning valuable land in key logistics hubs. | chat_gpt,google |
| REXR | Rexford Industrial Realty, Inc. focuses on industrial properties in land-constrained markets, benefiting from the scarcity of land. | chat_gpt |
| SPG | Simon Property Group, as the largest retail REIT, owns valuable land under its malls and outlets, benefiting from its real estate assets. | chat_gpt,google |
| TRNO | Terreno Realty Corporation focuses on acquiring, owning, and operating industrial real estate in major coastal markets, benefiting from land scarcity. | chat_gpt |
| WY | Weyerhaeuser operates in the timberland business, owning substantial land that can be used for various purposes, including real estate development. | chat_gpt,claude |
| CPT |  | claude,google |
| DLR |  | claude,google |
| EQIX |  | claude,google |
| GLPI |  | claude |
| NXRT |  | claude |
| RYN |  | claude |
| SBAC |  | claude |
| VICI |  | claude |
| CMG |  | twitter |
| MHO |  | twitter |
| NVR |  | twitter |
| PHM |  | twitter |
| TMHC |  | twitter |
| DOC |  | google |
| IRM |  | google |
| MAA |  | google |
| SHO |  | google |
| SKT |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/land/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/land" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
