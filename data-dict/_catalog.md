# External source directory

## What this file is

`data-dict/` has two layers. The numbered entries (`cfps.md`, `charls.md`, `industrial-firms.md`, `pollution-monitoring.md`) are dossiers, each covering one source in the four sections this directory prescribes. This file is the second layer: a pointer to an external directory that answers the earlier question, "does a source even exist for what I want to study, and where do I get it?"

The external directory is **Econ Datalab**, a field guide to data for economic research maintained by Zhiren Hu and Xuanqi Tong. At the snapshot taken here it holds 1333 sources across 7 regions and 16 topics, with 7735 linked application papers. It is a static site with no tracking.

- Live site: <https://econ-data.github.io/>
- Source repository: <https://github.com/econ-data>

Sections are numbered region.type.serial: `1.6.1` is region 1 (China), type 6 (environment), serial 1 (air pollution).

## How the two layers relate

They are not substitutes, and neither one is the "real" one.

| Layer | Answers | Density |
|---|---|---|
| Numbered entries here | What is inside this source and how do people get it wrong | Four sections, variable names, definition drift, merge keys, access route |
| Econ Datalab | Which sources exist at all, and where to obtain them | One summary, access links, application literature per source |

The rule is: search the catalogue to find the source; if you are going to use it for more than one project, write a numbered entry here and keep both. The catalogue tells you the source exists. Only an entry tells the next person that its income variable changed definition in 2016.

## How to query it

From the repository root:

```bash
python scripts/lookup_source.py CFPS
python scripts/lookup_source.py --region 中国数据 --topic 环境数据
python scripts/lookup_source.py --id 1.6.1
python scripts/lookup_source.py --list-topics
```

The script caches the directory under the user cache directory and refreshes it when it is a week old; `--refresh` forces a re-download. If the network is unavailable it says so and points at the live site rather than returning nothing.

## China data at a glance

The snapshot below is a convenience copy so that the coverage can be seen without a network call. The live site is authoritative; if the two disagree, the site is right.

| id | source | topic |
|---|---|---|
| `1.1.1` | 人口普查（Census） | 普查数据 |
| `1.1.2` | 全国经济普查 | 普查数据、微观企业数据 |
| `1.2.1` | 中国家庭追踪调查（CFPS） | 微观调查数据 |
| `1.2.2` | 中国家庭金融调查（CHFS） | 微观调查数据、金融数据 |
| `1.2.3` | 中国健康与养老追踪调查（CHARLS） | 微观调查数据、健康数据 |
| `1.2.4` | 中国综合社会调查（CGSS） | 微观调查数据 |
| `1.2.5` | 中国城镇住户调查（UHS） | 微观调查数据 |
| `1.2.6` | 中国农村固定观察点追踪调查（NFP） | 微观调查数据、农业数据 |
| `1.2.7` | 中国健康与营养调查（CHNS） | 微观调查数据、健康数据 |
| `1.2.8` | 中国居民收入分配调查（CHIP） | 微观调查数据 |
| `1.2.9` | 中国劳动力动态调查（CLDS） | 微观调查数据 |
| `1.2.10` | 中国时间利用调查 (China Time Use Survey，CTUS) | 微观调查数据 |
| `1.2.11` | 北京市居民出行调查 | 微观调查数据、交通数据 |
| `1.2.12` | 中国社会状况综合调查（Chinese Social Survey，CSS） | 微观调查数据 |
| `1.3.1` | 工业企业数据库 | 微观企业数据 |
| `1.3.2` | 企业排放数据库 | 微观企业数据 |
| `1.3.3` | 企业税收调查数据库 | 微观企业数据 |
| `1.3.4` | 专利数据库 | 微观企业数据 |
| `1.3.5` | 千家/万家企业节能行动名单 | 微观企业数据、能源数据 |
| `1.3.6` | 工商企业注册登记数据 | 微观企业数据 |
| `1.3.7` | 工业企业科技活动统计调查 | 微观企业数据 |
| `1.3.8` | 天眼查企业信息数据库 | 微观企业数据、商业数据 |
| `1.4.1` | 中国城市统计年鉴 | 区域经济数据 |
| `1.4.2` | 中国投入产出表 | 区域经济数据 |
| `1.4.3` | 中国县域统计年鉴 | 区域经济数据 |
| `1.4.4` | 中国统计年鉴与中国区域经济统计年鉴 | 区域经济数据 |
| `1.4.5` | 中国历史人口与田赋统计（《中国人口史》、梁方仲《中国历代户口、田地、田赋统计》） | 区域经济数据 |
| `1.4.6` | 《新中国五十年统计资料汇编》 | 区域经济数据 |
| `1.4.7` | 中国分省份市场化指数（王小鲁、樊纲等） | 区域经济数据、政治数据 |
| `1.5.1` | 基础地理数据 | 地理数据 |
| `1.5.2` | 中国历史地理信息系统（CHGIS） | 地理数据 |
| `1.6.1` | 空气污染数据 | 环境数据 |
| `1.6.2` | 水体质量数据 | 环境数据 |
| `1.6.3` | 中国地面气象站观测数据 | 环境数据 |
| `1.6.4` | 生态环境部 12369 环保举报数据 | 环境数据、政治数据 |
| `1.6.5` | 美国驻华使领馆 PM2.5 监测数据 | 环境数据 |
| `1.6.6` | 中国环境年鉴与中国环境统计年鉴 | 环境数据 |
| `1.6.7` | 《中国近五百年旱涝分布图集》 | 环境数据 |
| `1.7.1` | 中国能源统计年鉴与中国电力年鉴 | 能源数据 |
| `1.8.1` | 中国疾病监测点系统（DSP）死因数据 | 健康数据 |
| `1.8.2` | 中国老年健康影响因素跟踪调查（Chinese Longitudinal Healthy Longevity Survey，CLHLS） | 健康数据、微观调查数据 |
| `1.9.1` | 中国人口移动与出行大数据（百度/腾讯迁徙、出租车与网约车轨迹、手机信令、地图 API） | 交通数据 |
| `1.10.1` | 中国官员信息数据 | 政治数据 |
| `1.10.2` | 中国公务员招聘数据 | 政治数据 |
| `1.10.3` | 人民日报数字档案 | 政治数据 |
| `1.10.4` | 北大法宝行政处罚数据库 | 政治数据、环境数据 |
| `1.10.5` | 明实录与清实录 | 政治数据 |
| `1.10.6` | 中国政府采购网合同与公告数据 | 政治数据、商业数据 |
| `1.10.7` | 中国裁判文书网（China Judgments Online） | 政治数据 |
| `1.11.1` | 房价数据 | 房地产数据 |
| `1.11.2` | 中国土地市场网土地出让数据 | 房地产数据 |
| `1.12.1` | 银联银行卡交易数据 | 金融数据、商业数据 |
| `1.12.2` | 万得（Wind）金融终端数据 | 金融数据、微观企业数据 |
| `1.12.3` | 中国债券市场官方信息披露（中国货币网 CFETS、中国结算） | 金融数据 |
| `1.12.4` | 清科私募通（Zero2IPO）创业投资与私募股权数据库 | 金融数据、微观企业数据 |
| `1.12.5` | 中国人民银行社会融资规模统计 | 金融数据 |
| `1.12.6` | 胡润百富榜（Hurun Rich List） | 金融数据、商业数据 |
| `1.13.1` | GfK 零售监测数据 | 商业数据 |
| `1.13.2` | 百度指数 | 商业数据 |
| `1.14.1` | 县级农业产量数据 | 农业数据 |
| `1.14.2` | 中国科学院人地系统主题数据库（分省农作物播种面积等） | 农业数据、区域经济数据 |
| `1.14.3` | 清代粮价资料库（宫中档粮价清单） | 农业数据、商业数据 |
| `1.15.1` | 海关进出口数据库 | 贸易数据 |
| `1.16.1` | 中国教育追踪调查（CEPS） | 教育数据、微观调查数据 |
| `1.16.2` | 中国高考数据 | 教育数据、微观调查数据 |
| `1.16.3` | 中国大学生调查数据 | 教育数据、微观调查数据 |
| `1.16.4` | 《明清进士题名碑录索引》 | 教育数据、政治数据 |

Titles are kept in Chinese on purpose: this is how these sources are named in Chinese, in the documents that describe them, and in the conversations where someone asks about them. Translating the title makes the source harder to find, not easier.

## What is still missing here

Of the 67 China sources in the snapshot, four have a dossier in this directory. The rest are candidates, not gaps: a source earns an entry when someone has actually used it and lost time to it. Add one by following the procedure in `README.md`, and leave the catalogue entry alone.
