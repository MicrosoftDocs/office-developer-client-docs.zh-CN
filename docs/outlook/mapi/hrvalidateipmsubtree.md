---
title: HrValidateIPMSubtree
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrValidateIPMSubtree
api_type:
- COM
ms.assetid: 6454c1fa-5216-4934-a908-48c634ac4a07
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cf51985e534434c584eff4d63dfbf239121ee85
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436571"
---
# <a name="hrvalidateipmsubtree"></a>HrValidateIPMSubtree

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 IPM 文件夹 (标准) 邮件添加到邮件存储。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrValidateIPMSubtree(
  LPMDB lpMDB,
  ULONG ulFlags,
  ULONG FAR * lpcValues,
  LPSPropValue FAR * lppProps,
  LPMAPIERROR FAR * lppMapiError
);
```

## <a name="parameters"></a>参数

 _lpMDB_
  
> [in]指向要添加文件夹的邮件存储对象的指针。 
    
 _ulFlags_
  
> [in]用于控制文件夹创建方式的标志的位掩码。 可以设置以下标志：
    
MAPI_FORCE_CREATE 
  
> 文件夹应在创建之前进行验证，即使邮件存储属性指示它们有效。 当错误指示现有文件夹的结构已损坏时，客户端应用程序通常会设置此标志。 
    
MAPI_FULL_IPM_TREE 
  
> 应在邮件存储的根文件夹中创建完整的 IPM 文件夹集。 层次结构中的文件夹标题为：
    
    - 文件夹视图
    
    - 通用视图
    
    - 搜索根\*
    
    - IPM 子树\*
    
    - Inbox
    
    - 发件箱
    
    - 已删除项目\*
    
    - 已发送邮件
    
    其中，标记有 的三个文件夹是即使尚未设置 MAPI_FULL_IPM_TREE 标记，也创建 \* 的最小文件夹集。 当要创建文件夹的邮件存储是默认存储时，客户端应用程序通常会设置此标志。
    
 _lpcValues_
  
> [in， out]指向 _lppProps_ 参数中返回的数组中的 [SPropValue](spropvalue.md)结构数的指针。 如果 _lppProps_ 为 NULL，_则 lpcValues_ 参数的值可以是零。 
    
 _lppProps_
  
> [in， out]指向包含 **PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) 属性和相应文件夹条目标识符属性的属性值的 **SPropValue** 结构的数组的指针。 如果 **HrValidateIPMSubtree** 在邮件存储中创建了收件箱， **则 SPropValue** 数组将包含一个收件箱条目标识符，其特殊属性标记编码为  `PROP_TAG(PT_BINARY, PROP_ID_NULL)` 。 _lppProps_ 参数可以是 NULL，指示调用实现不需要返回 **SPropValue** 数组。 
    
 _lppMapiError_
  
> [out]指向包含错误的版本、组件和上下文信息的 [MAPIERROR](mapierror.md) 结构的指针。 如果未返回 **MAPIERROR** 结构，则 _lppMAPIError_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

MAPI 在内部使用 **HrValidateIPMSubtree** 函数，在首次打开邮件存储或将存储设置为默认存储时，在邮件存储中构造标准 IPM 子树。 客户端应用程序还可使用此功能验证或修复标准邮件文件夹。 
  
 **HrValidateIPMSubtree** 始终在存储的根文件夹中创建搜索根目录和 IPM 子树文件夹，在 IPM 子树文件夹中创建"已删除邮件"文件夹。 IPM 子树文件夹是邮件存储中 IPM 层次结构的根。 搜索根文件夹可以用作搜索结果文件夹的子树的根目录。 
  
IPM 客户端应显示其文件夹视图，从 IPM 子树根文件夹开始，并在其下方显示子文件夹。 邮件存储的根文件夹中的信息不应显示在客户端的用户界面中。 此功能意味着，如果客户端必须隐藏信息，则信息可以放入 IPM 子树根目录（用户看不到该目录）。 相反，要求用户看不到邮件和文件夹的非 IPM 应用程序（例如，在基于服务器的邮件存储中）可以将它们置于 IPM 层次结构之外。 
  
 **HrValidateIPMSubtree** 设置 **PR_VALID_FOLDER_MASK** 属性，以指示它创建的每个 IPM 文件夹是否具有有效的条目标识符。 邮件存储的以下条目标识符属性设置为相应文件夹的条目标识符，在 _lppProps_ 参数中返回 **，PR_VALID_FOLDER_MASK：** 
  
 **PR_COMMON_VIEWS_ENTRYID (** [PidTagCommonViewsEntryId)](pidtagcommonviewsentryid-canonical-property.md)
  
> **PR_FINDER_ENTRYID (** [PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 
  
> **PR_IPM_OUTBOX_ENTRYID (** [PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 
  
> **PR_IPM_SENTMAIL_ENTRYID (** [PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) 
  
> **PR_IPM_SUBTREE_ENTRYID (** [PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 
  
> **PR_IPM_WASTEBASKET_ENTRYID (** [PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 
  
> **PR_VIEWS_ENTRYID (** [PidTagViewsEntryId)](pidtagviewsentryid-canonical-property.md)
  
> IPM [收件箱PROP_TAG](prop_tag.md) 的占位符 (PT_BINARY PROP_ID_NULL) 。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MstStoreDlg.cpp  <br/> |CMsgStoreDlg：：OnValidateIPMSubtree  <br/> |MFCMAPI 使用 **HrValidateIPMSubtree** 方法将标准文件夹添加到邮件存储。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

