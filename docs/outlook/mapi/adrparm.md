---
title: ADRPARM
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ADRPARM
api_type:
- COM
ms.assetid: 35cd57b4-9901-456c-bf06-1f84e274eb4e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9663a25a50d914f47cff48124898d16318bbbc43
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425895"
---
# <a name="adrparm"></a>ADRPARM

**适用于**：Outlook 2013 | Outlook 2016 
  
描述 "常用地址" 对话框的显示和行为。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _ADRPARM
{
  ULONG cbABContEntryID;
  LPENTRYID lpABContEntryID;
  ULONG ulFlags;
  LPVOID lpReserved;
  ULONG ulHelpContext;
  LPSTR lpszHelpFileName;
  LPFNABSDI lpfnABSDI;
  LPFNDISMISS lpfnDismiss;
  LPVOID lpvDismissContext;
  LPSTR lpszCaption;
  LPSTR lpszNewEntryTitle;
  LPSTR lpszDestWellsTitle;
  ULONG cDestFields;
  ULONG nDestFieldFocus;
  LPSTR FAR *lppszDestTitles;
  ULONG FAR *lpulDestComps;
  LPSRestriction lpContRestriction;
  LPSRestriction lpHierRestriction;
} ADRPARM, FAR *LPADRPARM;

```

## <a name="members"></a>Members

**cbABContEntryID**
  
> 由**lpABContEntryID**指向的条目标识符中的字节数。
    
**lpABContEntryID**
  
> 指向提供 "地址" 对话框中显示的收件人地址的初始列表的容器的条目标识符的指针。
    
**ulFlags**
  
> 与各种地址对话框选项关联的标志的位掩码。 可以设置以下标志:
    
AB_RESOLVE
  
> 启用 "地址" 对话框关闭后要解析的所有名称。 如果名称解析过程中存在不明确的条目, 则会出现一个对话框提示用户解决这些错误。 设置此标志可确保[IAddrBook:: Address](iaddrbook-address.md)返回的所有名称均已解析。 
    
AB_SELECTONLY
  
> 禁止为收件人列表创建一次性地址。 仅当对话框是模式时, 才使用此标志, 正如设置的 DIALOG_MODAL 标志所指示的那样。
    
ADDRESS_ONE
  
> 用户只能从列表中选择一个收件人, 而不是多个收件人。 仅当**cDestFields**为零时, 并且对话框是模式的 (由设置的 DIALOG_MODAL 标志指示) 时, 此标志才有效。 
    
DIALOG_MODAL
  
> 显示 "常用地址" 对话框的模式版本。 应设置此标志或 DIALOG_SDI;不能同时设置它们。 
    
DIALOG_OPTIONS
  
> 使 "**发送选项**" 按钮显示在对话框中。 仅当对话框是模式时, 才使用此标志, 正如设置的 DIALOG_MODAL 标志所指示的那样。 
    
DIALOG_SDI
  
> 导致显示 "常用地址" 对话框的无模式版本。 应设置此标志或 DIALOG_MODAL;不能同时设置它们。 对于非 Outlook 客户端, 将忽略 DIALOG_SDI 标志, 将显示对话框的模式版本。 因此, 在[IAddrBook:: Address](iaddrbook-address.md)的_lpulUIParam_参数中, 指向句柄的指针不应是预期的。
    
**lpReserved**
  
> 保留, 必须为零。
    
**ulHelpContext**
  
> 指定在 "**帮助**" 中的上下文, 当用户单击 "地址" 对话框中的 "帮助" 按钮时将首先显示该上下文。 
    
**lpszHelpFileName**
  
> 指向将与 "地址" 对话框关联的帮助文件的名称的指针。 **lpszHelpFileName**成员与**ulHelpContext**一起使用, 以调用 Windows **WinHelp**函数。 
    
**lpfnABSDI**
  
> 指向基于[ACCELERATEABSDI](accelerateabsdi.md)原型的 MAPI 函数的指针或 NULL。 此成员仅适用于对话框的无模式版本, 如设置的 DIALOG_SDI 标志所指示的那样。 生成要传递给 IAddrBook 的**ADRPARM**结构的客户端[:: Address](iaddrbook-address.md)必须始终将**lpfnABSDI**成员设置为 NULL。 如果设置了 DIALOG_SDI 标志, MAPI 将在返回之前将其设置为有效的函数。 客户端在其邮件循环中调用此函数, 以确保 "通讯簿" 对话框中的 "加速器正常工作"。 当对话框被解除, 并且 MAPI 调用由**lpfnDismiss**成员指向的函数时, 客户端应从其邮件循环解除**ACCELERATEABSDI**函数的挂钩。 
    
**lpfnDismiss**
  
> 指向基于[DISMISSMODELESS](dismissmodeless.md)原型的函数的指针或 NULL。 此成员仅适用于对话框的无模式版本, 如设置的 DIALOG_SDI 标志所指示的那样。 MAPI 在用户消除无模式地址对话框时调用**DISMISSMODELESS**函数, 通知客户端调用了对话框不再处于活动状态的**IAddrBook:: address** 。 
    
**lpvDismissContext**
  
> 指向要传递给**lpfnDismiss**成员指向的**DISMISSMODELESS**函数的上下文信息的指针。 此成员仅适用于对话框的无模式版本, 正如设置的 DIALOG_SDI 标志所指示的那样。 
    
**lpszCaption**
  
> 指向要用作 "常用地址" 对话框标题的文本的指针。
    
**lpszNewEntryTitle**
  
> 指向要用作按钮的按钮标签的文本的指针, 该按钮用于调用 "**新建项**" 对话框或其他对话框。 
    
**lpszDestWellsTitle**
  
> 指向要用作 "常用地址" 对话框的模式版本中可显示的收件人文本框控件标题的文本的指针。 此成员不用于无模式对话框。 
    
**cDestFields**
  
> "地址" 对话框的 "模式" 版本中的收件人文本框控件的计数; 如果对话框为无模式, 则为零。 仅当满足以下条件时, 才会打开 "地址" 对话框进行浏览: 
    
  - **cDestFields**成员设置为零。 
    
  - 设置了 DIALOG_BOX 标志。
    
  - 未设置 ADDRESS_ONE 标志。
    
  将**cDestFields**设置为0xffffffff 意味着 MAPI 应创建默认数量的收件人文本框控件。 在这种情况下, **lppszDestTitles**和**lpulDestComps**成员必须为 NULL。 
    
**nDestFieldFocus**
  
> 指示在显示对话框的模式版本时, 应具有初始焦点的特定文本框控件。 此值必须介于0和**cDestFields**的值减1之间。 
    
**lppszDestTitles**
  
> 指向与在 "地址" 对话框的 "模式" 版本中显示的每个文本框控件相关联的按钮的标签数组的指针。 **cDestFields**成员的值指示数组中包含的标签数。 如果**lppszDestTitles**成员为 NULL, 则**Address**方法使用默认标题。 
    
**lpulDestComps**
  
> 指向收件人类型值 (如 MAPI_TO、MAPI_CC 和 MAPI_BCC) 的数组的指针, 这些值与每个文本框控件相关联。 **CDestFields**成员的值指示包含在数组中的收件人类型的数量。 **lpulDestComps**所指向的值可用于设置每个收件人的**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。 如果**lpulDestComps**成员为 NULL, 则**Address**方法使用默认的收件人类型。 
    
**lpContRestriction**
  
> 指向限制可在对话框中显示的地址条目类型的[SRestriction](srestriction.md)结构的指针。 
    
**lpHierRestriction**
  
> 指向一个**SRestriction**结构的指针, 该结构限制可提供要在对话框中显示的地址条目的通讯簿容器。 
    
## <a name="remarks"></a>说明

客户端和服务提供程序使用**ADRPARM**结构控制 MAPI 常用地址对话框的外观和行为。 "地址" 对话框有两种种类: 无模式和模式。 **ADRPARM**结构中的某些成员适用于对话框的两个版本, 但有些仅适用于这两个版本之一。 下表将**ADRPARM**结构的成员与公用地址对话框的使用关联起来。 
  
|ADRPARM 成员|"对话框类型"|
|:-----|:-----|
|**cbABContEntryID**和**lpABContEntryID** <br/> |模式和无模式  <br/> |
|**ulFlags** <br/> |模式和无模式  <br/> |
|**lpReserved** <br/> |模式和无模式  <br/> |
|**ulHelpContext**和**lpszHelpFileName** <br/> |模式和无模式  <br/> |
|**lpfnABSDI** <br/> |Modeless  <br/> |
|**lpfnDismiss**和**lpvDismissContext** <br/> |Modeless  <br/> |
|**lpszCaption** <br/> |模式和无模式  <br/> |
|**lpszNewEntryTitle** <br/> |Modal  <br/> |
|**lpszDestWellsTitle**、 **cDestFields**、 **nDestFieldFocus**、 **lppszDestTitles**和**lpulDestComps** <br/> |Modal  <br/> |
|**lpContRestriction** <br/> |模式和无模式  <br/> |
|**lpHierRestriction** <br/> |模式和无模式  <br/> |
   
无模式对话框是一个只读的条目, 显示来自一个或多个通讯簿容器。 对话框可以显示选定容器中的所有条目, 也可以仅限于那些与限制建立的条件相匹配的条目和容器。 **lpContRestriction**指向的内容限制可以限制所显示的条目类型和**lpHierRestriction**指向的层次结构限制。可以限制提供这些条目的容器。 若要在对话框关闭时通知呼叫者, MAPI 将调用由与[DISMISSMODELESS](dismissmodeless.md)原型匹配的呼叫者提供的函数。 另一个与[ACCELERATEABSDI](accelerateabsdi.md)原型匹配的函数由 MAPI 提供, 由 Windows 消息循环中的调用方调用, 以促进键盘快捷方式的使用。 当客户端调用[IAddrBook:: address](iaddrbook-address.md)或 service providers 调用[IMAPISupport:: address](imapisupport-address.md)时, 可以显示 MAPI 地址对话框的无模式版本。 
  
模式对话框是一个读/写显示来自一个或多个容器的条目。 在**lpContRestriction**和**lpHierRestriction**成员中设置限制时, 其内容会受到与无模式版本相同的影响。 除了显示容器条目的列表框之外, 模式对话框还可以包含一个和三个用于保存用户选择的条目的文本框控件。 每个编辑控件都与特定的收件人类型或**PR_RECIPIENT_TYPE**属性 (如 MAPI_TO) 相关联。 可以通过任一**地址**方法或在客户端调用 IAddrBook 时显示 "模式地址" 对话框[::D etails](iaddrbook-details.md)和服务提供程序调用[IMAPISupport::D etails](imapisupport-details.md)。 
  
此图包含两个文本框控件, 因为控制此对话框的显示的**ADRPARM**结构的**cDestFields**成员设置为2。 第一个控件具有初始焦点, 因为**nDestFieldFocus**成员设置为0。 
  
**lpszNewEntryTitle**成员指向按钮标签的文本, 当选择该按钮时, 会显示一个附加对话框。 通常, 如模式对话框的插图中所示, 按钮标为 "**新建**", 并且出现的对话框列出可由配置文件中的任何通讯簿提供程序创建的所有地址类型。 客户端通过调用[IAddrBook:: NewEntry](iaddrbook-newentry.md)并为_cbEidNewEntryTpl_参数传递零来显示此**新条目**对话框, 并在用户选择按钮时为_lpEidNewEntryTpl_参数提供 NULL 值。 此对话框中包含的信息来自 MAPI 一次性表。 
  
此对话框中的每个条目都与一个模板相关联, 用于输入创建特定类型的地址所需的数据。 大多数通讯簿提供程序为其可以创建的每种类型的地址条目提供一个模板。 当用户从该对话框中进行选择时, MAPI 将显示相应的模板。
  
**ADRPARM**结构的**ulFlags**成员最重要的四位包含一个版本号, 用于标识**ADRPARM**结构的版本。 当前版本为 0 (零) 或 ADRPARM_HELP_CTX。 对于除零之外的任何结构版本, MAPI 的当前实现将会失败。 
  
结构的未来版本可能完全不同;它们可能不支持版本-零结构。 提供以下宏是为了从**ulFlags**成员中提取版本号, 并将其与定义的标志组合在一起: 
  
- **GET_ADRPARM_VERSION**(_ulFlags_) 
- **SET_ADRPARM_VERSION**(_ulFlags_, _ ulVersion _) 
- **ADRPARM_HELP_CTX**
  
## <a name="see-also"></a>另请参阅

- [ACCELERATEABSDI](accelerateabsdi.md)
- [DISMISSMODELESS](dismissmodeless.md)
- [IAddrBook::Address](iaddrbook-address.md)
- [IMAPISupport::Address](imapisupport-address.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

