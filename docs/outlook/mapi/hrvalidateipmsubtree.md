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
ms.openlocfilehash: 8b6d4fa1d9ffa6ab5f800bad9f02ac5aa9abd8c0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775188"
---
# <a name="hrvalidateipmsubtree"></a>HrValidateIPMSubtree

  
  
**适用于**： Outlook 
  
将标准人际邮件 (IPM) 文件夹添加到的消息存储。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
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
  
> [in]指向邮件存储要向其中添加文件夹的对象。 
    
 _ulFlags_
  
> [in]用于控制如何创建的文件夹的标志位掩码。 可以设置以下标志：
    
MAPI_FORCE_CREATE 
  
> 之前创建，应验证文件夹，即使它们是有效的消息存储库属性指示。 一个错误，指示已损坏的现有文件夹结构时，客户端应用程序通常设置此标志。 
    
MAPI_FULL_IPM_TREE 
  
> 消息存储库的根文件夹中，应创建整套 IPM 文件夹。 层次结构中的文件夹标题是：
    
    - 文件夹视图
    
    - 公共视图
    
    - 搜索根\*
    
    - IPM 子树\*
    
    - Inbox
    
    - 发件箱
    
    - 已删除的项目\*
    
    - 已发送的邮件
    
    三个文件夹与标记的位置\*是最小集创建即使 MAPI_FULL_IPM_TREE 标志尚未设置。 客户端应用程序通常将在其中的文件夹是要创建的消息存储时的默认存储设置此标志。
    
 _lpcValues_
  
> [传入、 传出]指向[SPropValue](spropvalue.md)结构_lppProps_参数中返回的数组中的编号的指针。 _LpcValues_参数的值可以是零，如果_lppProps_为 NULL。 
    
 _lppProps_
  
> [传入、 传出]为指向包含属性值为**PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) 属性以及相应的文件夹条目标识符属性的**SPropValue**结构数组的指针。 如果**HrValidateIPMSubtree**消息存储库中创建收件箱， **SPropValue**数组包括收件箱条目标识符，其中编码为一个特殊属性标记`PROP_TAG(PT_BINARY, PROP_ID_NULL)`。 _LppProps_参数可以是 NULL，表明调用实现不需要返回**SPropValue**数组。 
    
 _lppMapiError_
  
> [输出]为包含错误的版本、 组件及上下文信息[MAPIERROR](mapierror.md)结构指针的指针。 如果不返回任何**MAPIERROR**结构_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

MAPI 内部使用**HrValidateIPMSubtree**函数来构造中的消息存储的标准 IPM 子树时首先打开的存储，或者存储区进行的默认存储。 此函数还可通过客户端应用程序以验证或修复标准邮件文件夹。 
  
 **HrValidateIPMSubtree**始终存储的根文件夹和 IPM 子树文件夹中的已删除邮件文件夹中创建的搜索根和 IPM 子树文件夹。 IPM 子树的文件夹是该消息存储中 IPM 层次结构的根。 搜索根文件夹可以用作搜索结果文件夹的子树的根。 
  
IPM 客户端应该显示开头 IPM 子树的根文件夹和显示在它下面的文件夹的子其文件夹视图。 在客户端的用户界面中不应出现的消息存储的根文件夹中的信息。 此功能意味着，如果客户端必须隐藏信息，请信息可以放置在 IPM 子树的根目录，其中不对用户可见。 相比之下，需要邮件和文件夹，使其与用户，例如基于服务器的邮件存储区中，不可见的非 IPM 应用程序可以将它们放外 IPM 层次结构。 
  
 **HrValidateIPMSubtree**设置**PR_VALID_FOLDER_MASK**属性，以指示它创建每个 IPM 文件夹是否具有有效项标识符。 消息存储库的下列条目标识符属性设置为相应的文件夹中的项标识符，以及**PR_VALID_FOLDER_MASK** _lppProps_参数中返回： 
  
 **PR_COMMON_VIEWS_ENTRYID**([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))
  
> **PR_FINDER_ENTRYID**([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))
  
> **PR_IPM_OUTBOX_ENTRYID**([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))
  
> **PR_IPM_SENTMAIL_ENTRYID**([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))
  
> **PR_IPM_SUBTREE_ENTRYID**([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))
  
> **PR_IPM_WASTEBASKET_ENTRYID**([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))
  
> **PR_VIEWS_ENTRYID**([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))
  
> 占位符[PROP_TAG](prop_tag.md) IPM 收件箱 （PT_BINARY、 PROP_ID_NULL）。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MstStoreDlg.cpp  <br/> |CMsgStoreDlg::OnValidateIPMSubtree  <br/> |MFCMAPI 使用**HrValidateIPMSubtree**方法将标准文件夹添加到的消息存储。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

