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
  
将标准人际邮件 (IPM) 文件夹添加到邮件存储区。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
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
  
> 实时指向要向其添加文件夹的邮件存储对象的指针。 
    
 _ulFlags_
  
> 实时用于控制创建文件夹的标志的位掩码。 可以设置以下标志:
    
MAPI_FORCE_CREATE 
  
> 应在创建文件夹之前对其进行验证, 即使邮件存储库属性指示它们是有效的也是如此。 当错误指示现有文件夹的结构已损坏时, 客户端应用程序通常会设置此标志。 
    
MAPI_FULL_IPM_TREE 
  
> 应在邮件存储区的根文件夹中创建完整的 IPM 文件夹集。 层次结构中的文件夹标题为:
    
    - 文件夹视图
    
    - 常用视图
    
    - 搜索根\*
    
    - IPM 子树\*
    
    - Inbox
    
    - 发件箱
    
    - 已删除项目\*
    
    - 已发送邮件
    
    其中, 使用\*标记的三个文件夹是创建的最小集, 即使尚未设置 MAPI_FULL_IPM_TREE 标志也是如此。 当要在其中创建文件夹的邮件存储是默认存储时, 客户端应用程序通常会设置此标志。
    
 _lpcValues_
  
> [in, out]一个指针, 指向_lppProps_参数中返回的数组中的[SPropValue](spropvalue.md)结构的数目。 如果_lppProps_为 NULL, 则_lpcValues_参数的值可以为零。 
    
 _lppProps_
  
> [in, out]指向**SPropValue**结构数组的指针, 该数组包含**PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) 属性和相应的文件夹项标识符属性的属性值。 如果**HrValidateIPMSubtree**在邮件存储区中创建收件箱, 则**SPropValue**数组包含一个带有编码为`PROP_TAG(PT_BINARY, PROP_ID_NULL)`的特殊属性标记的收件箱条目标识符。 _lppProps_参数可以为 NULL, 指示调用实现不要求返回**SPropValue**数组。 
    
 _lppMapiError_
  
> 排除指向包含错误的版本、组件和上下文信息的[MAPIERROR](mapierror.md)结构的指针的指针。 如果不返回**MAPIERROR**结构, 则将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

MAPI 在内部使用**HrValidateIPMSubtree**函数在首次打开存储库时或在将存储创建为默认存储时在邮件存储中构建标准的 IPM 子树。 客户端应用程序还可以使用此函数验证或修复标准邮件文件夹。 
  
 **HrValidateIPMSubtree**始终在存储区的根文件夹和 ipm 子树文件夹中的 "已删除邮件" 文件夹中创建搜索根和 IPM 子树文件夹。 ipm 子树文件夹是该邮件存储区中 ipm 层次结构的根。 搜索根文件夹可用作搜索结果文件夹的子树的根文件夹。 
  
IPM 客户端应显示其文件夹视图 (从 IPM 子树根文件夹开始, 并在其下显示子文件夹)。 邮件存储区的根文件夹中的信息不应出现在客户端的用户界面中。 此功能意味着, 如果客户端必须隐藏信息, 则可以将信息放在 IPM 子树根目录中, 该目录对用户是不可见的。 相比之下, 要求邮件和文件夹对用户不可见的非 IPM 应用程序 (例如, 在基于服务器的邮件存储区中) 可以将它们放在 IPM 层次结构之外。 
  
 **HrValidateIPMSubtree**设置**PR_VALID_FOLDER_MASK**属性, 以指示它所创建的每个 IPM 文件夹是否都有一个有效的条目标识符。 邮件存储区的以下条目标识符属性将设置为相应文件夹的条目标识符, 并在_lppProps_参数中返回, 以及**PR_VALID_FOLDER_MASK**: 
  
 **PR_COMMON_VIEWS_ENTRYID**([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))
  
> **PR_FINDER_ENTRYID**([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))
  
> **PR_IPM_OUTBOX_ENTRYID**([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))
  
> **PR_IPM_SENTMAIL_ENTRYID**([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))
  
> **PR_IPM_SUBTREE_ENTRYID**([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))
  
> **PR_IPM_WASTEBASKET_ENTRYID**([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))
  
> **PR_VIEWS_ENTRYID**([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))
  
> 用于 IPM 收件箱的占位符[PROP_TAG](prop_tag.md) (PT_BINARY, PROP_ID_NULL)。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MstStoreDlg  <br/> |CMsgStoreDlg:: OnValidateIPMSubtree  <br/> |MFCMAPI 使用**HrValidateIPMSubtree**方法将标准文件夹添加到邮件存储区。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

