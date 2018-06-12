---
title: DTCTL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTCTL
api_type:
- COM
ms.assetid: 6d1589e9-b171-427a-9a3e-b4154ee8ceb6
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 68c621f5f73073ed127767cc1db189769dab227d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774881"
---
# <a name="dtctl"></a>DTCTL

**适用于**： Outlook 
  
描述将显示表中生成的对话框中使用的控件。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct
{
  ULONG ulCtlType;
  ULONG ulCtlFlags;
  LPBYTE lpbNotif;
  ULONG cbNotif;
  LPSTR lpszFilter;
  ULONG ulItemID;
  union
  {
    LPVOID lpv;
    LPDTBLLABEL lplabel;
    LPDTBLEDIT lpedit;
    LPDTBLLBX lplbx;
    LPDTBLCOMBOBOX lpcombobox;
    LPDTBLDDLBX lpddlbx;
    LPDTBLCHECKBOX lpcheckbox;
    LPDTBLGROUPBOX lpgroupbox;
    LPDTBLBUTTON lpbutton;
    LPDTBLRADIOBUTTON lpradiobutton;
    LPDTBLMVLISTBOX lpmvlbx;
    LPDTBLMVDDLBX lpmvddlbx;
    LPDTBLPAGE lppage;
  } ctl;
} DTCTL, FAR *LPDTCTL;

```

## <a name="members"></a>成员

**ulCtlType**
  
> 包含**ctl**成员，并且对应于控件的**PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性的控件的类型。 可能值如下所示：
    
DTCT_LABEL 
  
> 标签控件。
    
DTCT_EDIT 
  
> 编辑控件。
    
DTCT_LBX 
  
> 列表框控件。
    
DTCT_COMBOBOX 
  
> 组合框控件。
    
DTCT_DDLBX 
  
> 下拉列表控件。
    
DTCT_CHECKBOX 
  
> 复选框控件。
    
DTCT_GROUPBOX 
  
> 分组框控件。
    
DTCT_BUTTON 
  
> 按钮控件。
    
DTCT_PAGE 
  
> 选项卡式的页面控件。
    
DTCT_RADIOBUTTON 
  
> 单选按钮控件。
    
DTCT_MVLISTBOX 
  
> 多值的列表控件。
    
DTCT_MVDDLBX 
  
> 多值的下拉列表控件。
    
**ulCtlFlags**
  
> 位掩码的标志，描述控件的功能，并对应于控件的**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性。 这些标志的复选框、 组合框或列表框中，可以设置和编辑控件仅。 可能值如下所示：
    
DT_ACCEPT_DBCS 
  
> ANSI 或 DBCS 格式是可接受。 此标志是有效的编辑控件仅。
    
DT_EDITABLE 
  
> 用户可以修改控件中的文本。 
    
DT_MULTILINE 
  
> 控件可以包含多个文本行。 此标志是有效的编辑控件仅。
    
DT_PASSWORD_EDIT 
  
> 控件包含密码;因此，控件的内容不应显示给用户。 此标志是有效的编辑控件仅。
    
DT_REQUIRED 
  
> 对话框控件是必需的。 此标志是仅对编辑和组合框控件有效。
    
DT_SET_IMMEDIATE 
  
> 启用即时输出时控件中更改的值。 这样，同时建立两个控件之间的依赖关系。 
    
**lpbNotif**
  
> 指向结构组成的[GUID](guid.md)结构，以表示服务提供商和控件的标识符。 **LpbNotif**和**cbNotif**成员对应于控件的**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性，用于在控件具有要更新时通知用户界面。
    
**cbNotif**
  
> 由**lpbNotif**成员指向结构中的字节数。 
    
**lpszFilter**
  
> 指向介绍可以编辑或组合框控件中输入的字符的字符串。 对于其他类型的控件， **lpszFilter**成员可以为 NULL。 对于编辑和组合框控件，它应为每次应用于单个字符的正则表达式。 相同的筛选器应用于该控件中的所有字符。 筛选器字符串的格式如下所示： 
    
|**字符**|**说明**|
|:-----|:-----|
| `*` <br/> | 允许任何字符 (例如， `"*"`)。  <br/> |
| `[ ]` <br/> |定义一组字符 (例如， `"[0123456789]"`。)  <br/> |
| `-` <br/> |指示某个范围的字符 (例如， `"[a-z]"`)。  <br/> |
| `~` <br/> |指示不允许这些字符 (例如， `"[~0-9]")`。 <br/>|   
| `\` <br/> |用于 quote 任何以前符号 (例如，`"[\-\\\[\]]"`是指-， \, [，和] 允许字符)。  <br/> |
   
**ulItemID**
  
> 标识对话框资源中的控件的值。 对于类型 DTCT_PAGE **ulItemID**的选项卡式的页面控件成员 （可选） 用于从字符串资源加载页面组件名称。 位置和标签信息读取对话框资源。 
    
**ctl**
  
> 一个包含控件的数据，并且与控件的**PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) 属性相对应的结构。 每种类型的控件具有不同的结构。
    
## <a name="remarks"></a>备注

**DTCTL**结构描述任何类型的一个控件。 大部分及其成员用于为控件设置属性。 
  
**Ctl**成员的结构与特定类型的控制相关的联合。 如果**DTCTL**结构描述编辑控件，例如， **ctl**成员将指向[DTBLEDIT](dtbledit.md)结构。 此结构对应于控件的**PR_CONTROL_STRUCTURE**属性。 联合具有作为其第一个成员 LPVOID 允许编译时间初始化**DTCTL**结构的类型的变量。 
  
尽管[BuildDisplayTable](builddisplaytable.md)函数用于生成控件资源中的显示表使用**DTCTL**结构，但**DTCTL**结构永远不会显示表格本身中显示。 此结构仅信息提供给**BuildDisplayTable**。
  
**UlCtlFlags**成员，在四个标志 DT_ACCEPT_DBCS，DT_EDITABLE，DT_MULTILINE_and DT_PASSWORD_EDIT 影响编辑控件仅。 两个其他人 DT_REQUIRED DT_SET_IMMEDIATE 影响任何可编辑控件。 
  
可用的对话框中的控件的标签、 文本框、 墨迹感知文本框、 列表、 下拉列表、 组合框、 复选框、 组框、 按钮、 单选按钮和选项卡式的页面。
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅

- [BuildDisplayTable](builddisplaytable.md)
- [DTBLBUTTON](dtblbutton.md)
- [DTBLCHECKBOX](dtblcheckbox.md)
- [DTBLCOMBOBOX](dtblcombobox.md)
- [DTBLDDLBX](dtblddlbx.md)
- [DTBLEDIT](dtbledit.md)
- [DTBLGROUPBOX](dtblgroupbox.md)
- [DTBLLABEL](dtbllabel.md)
- [DTBLLBX](dtbllbx.md)
- [DTBLMVDDLBOX](dtblmvddlbox.md)
- [DTBLMVLISTBOX](dtblmvlistbox.md)
- [DTBLPAGE](dtblpage.md)
- [DTBLRADIOBUTTON](dtblradiobutton.md)
- [MAPI 结构](mapi-structures.md)

