# ODS-TalentPolicy
Open Data Series: City and Province Talent Policy.  
开源数据系列：城市和省级层面人才引进政策。

> This project is part of the [StataMCP-Team](https://team.statamcp.com)'s **STOP (StataMCP Team OpenData Projects)**.  
> All rights reserved by **StataMCP-Team** and **Shanghai BayesViews Co., Ltd. (上海比翼视界信息科技有限公司)**.  
> Any unauthorized redistribution or commercial use is strictly prohibited.  
> 本项目隶属于 [StataMCP-Team](https://team.statamcp.com) 的 **STOP（StataMCP 团队开源数据计划）**。  
> 版权所有 © **StataMCP-Team** 与 **上海比翼视界信息科技有限公司**。  
> 未经授权，禁止任何形式的二次分发或商业用途。
> 
> If there is any infringement, please [contact us](mailto:sepine@statamcp.com) for removal.

## Raw data source
该项目中所有源数据均来自各地方政府网站，源数据所有权利归各地方政府所有。
进一步的数据由[北大法宝](https://www.pkulaw.com)整理而得。
该项目中的数据为人工在北大法宝进行检索后人工二次整理所得，并对其进行系列[处理](#data-process)。

## Data process
在原始数据获得后，通过[city-parse](https://github.com/sepinetam/city-parse)中所提供的工具，基于小参数大模型进行关键信息提取并进行人工校对而得。  
具体流程如下：
1. 获取以“人才引进”作为检索结果的原始数据并将其整合为一个[csv文件](source/datas/raw.csv)
2. 使用[city-parse](https://github.com/sepinetam/city-parse)中的 `parse` 工具进行城市名称的提取
3. 删除省级行政单位样本（如浙江省、内蒙古自治区等，但保留直辖市）并按照时间排序
4. 保留城市首次出现的样本，得到最终[样本](source/datas/talent_policy.csv)

## Future plans
- 添加城市的六位编码
- 添加精简版和dta格式

## Descriptive statistics
- Time Span: 2011.01.01 - 2024.12.31
- Obs: 1809 (in raw), 318 (final data)

## License
[StataMCP-OpenData-Project-License](#)

如果在您的研究中使用了该数据请注明来源，可以使用如下的 `BibTex` 模版:
```
@dataset{stop2025_talentpolicy,
  author       = {StataMCP-Team},
  title        = {Open Data Series: City and Province Talent Policy},
  year         = {2025},
  howpublished = {\url{https://github.com/statamcp/ODS-TalentPolicy}},
}
```
