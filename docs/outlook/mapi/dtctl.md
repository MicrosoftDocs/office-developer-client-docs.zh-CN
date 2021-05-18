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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2a2ca1fba5dceb45b41c2f25a96e163f02c41440
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421499"
---
# <a name="dtctl"></a>DTCTL

**适用于**：Outlook 2013 | Outlook 2016 
  
描述将在基于显示表构建的对话框中使用的控件。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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

## <a name="members"></a>Members

**ulCtlType**
  
> 包含在 **ctl** 成员中的控件类型，对应于控件的 PR_CONTROL_TYPE ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性。  可能的值如下所示：
    
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
  
> 选项卡式页面控件。
    
DTCT_RADIOBUTTON 
  
> 单选按钮控件。
    
DTCT_MVLISTBOX 
  
> 多值列表控件。
    
DTCT_MVDDLBX 
  
> 多值下拉列表控件。
    
**ulCtlFlags**
  
> 描述控件功能并对应于控件的 PR_CONTROL_FLAGS ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 标志的位掩码。  只能为复选框、组合框、列表框和编辑控件设置这些标志。 可能的值如下所示：
    
DT_ACCEPT_DBCS 
  
> 接受 ANSI 或 DBCS 格式。 此标志仅对编辑控件有效。
    
DT_EDITABLE 
  
> 用户可以修改控件中的文本。 
    
DT_MULTILINE 
  
> 控件可以包含多个文本行。 此标志仅对编辑控件有效。
    
DT_PASSWORD_EDIT 
  
> 控件包含密码;因此，不应向用户显示控件的内容。 此标志仅对编辑控件有效。
    
DT_REQUIRED 
  
> 对话框控件是必需的。 此标志仅对编辑框和组合框控件有效。
    
DT_SET_IMMEDIATE 
  
> 启用在控件中更改时立即输出值。 这允许在两个控件之间建立依赖关系。 
    
**lpbNotif**
  
> 指向由 [GUID](guid.md) 结构组成的结构的指针，用于表示服务提供商和控件的标识符。 **lpbNotif** 和 **cbNotif** 成员对应于控件的 **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性，用于在必须更新控件时通知用户界面。
    
**cbNotif**
  
> **lpbNotif** 成员指向的结构中的字节数。 
    
**lpszFilter**
  
> 指向描述可在编辑或组合框控件中输入哪些字符的字符串的指针。 对于其他类型的控件 **，lpszFilter** 成员可以是 NULL。 对于编辑框和组合框控件，它应是一次应用于单个字符的正则表达式。 相同的筛选器将应用于控件中所有的字符。 筛选器字符串的格式如下： 
    
|**字符**|**说明**|
|:-----|:-----|
| `*` <br/> | 允许任何字符 (例如 `"*"` ，) 。  <br/> |
| `[ ]` <br/> |定义一组字符 (例如 `"[0123456789]"` ，.)   <br/> |
| `-` <br/> |指示一系列字符 (例如 `"[a-z]"` ，) 。  <br/> |
| `~` <br/> |指示不允许使用这些字符， (例如 ， `"[~0-9]")` 。 <br/>|   
| `\` <br/> |用于引用前面的任何符号 (例如，允许使用 `"[\-\\\[\]]"` -、[和 \, ] 字符) 。  <br/> |
   
**ulItemID**
  
> 用于标识对话框资源中的控件的值。 对于类型为 DTCT_PAGE的选项卡式页面控件，可以选择使用 **ulItemID** 成员从字符串资源加载页面的组件名称。 从对话框资源中读取位置和标签信息。 
    
**ctl**
  
> 一个包含控件数据的结构，与控件的 PR_CONTROL_STRUCTURE ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) 属性相对应。  每种类型的控件都有不同的结构。
    
## <a name="remarks"></a>备注

**DTCTL** 结构描述任何类型的一个控件。 它的大多数成员都用于设置控件的属性。 
  
**ctl** 成员是一组与特定类型控件相关的结构。 例如 **，如果 DTCTL** 结构描述编辑控件， **则 ctl** 成员将指向 [DTBLEDIT](dtbledit.md) 结构。 此结构对应于控件的 **PR_CONTROL_STRUCTURE** 属性。 该联合的第一个成员是 LPVOID 类型的变量，以允许 **DTCTL** 结构的编译时间初始化。 
  
尽管 [BuildDisplayTable](builddisplaytable.md) 函数使用 **DTCTL** 结构从控件资源生成显示表， **但 DTCTL** 结构永远不会显示在显示表本身中。 此结构只向 **BuildDisplayTable 提供信息**。
  
在 **ulCtlFlags** 成员中，DT_ACCEPT_DBCS、DT_EDITABLE、DT_MULTILINE_and DT_PASSWORD_EDIT四个标志仅影响编辑控件。 其他两DT_REQUIRED和DT_SET_IMMEDIATE可编辑控件。 
  
对话框可用的控件有标签、文本框、墨迹感知文本框、列表、下拉列表、组合框、复选框、分组框、按钮、单选按钮和选项卡式页面。
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
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

