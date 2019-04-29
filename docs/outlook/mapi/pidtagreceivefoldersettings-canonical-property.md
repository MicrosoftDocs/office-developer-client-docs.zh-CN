---
title: PidTagReceiveFolderSettings 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceiveFolderSettings
api_type:
- COM
ms.assetid: 2f0b1679-05b0-4580-b6d2-474fe3f9d012
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8590e357252089aaa49a71d443037b9b9ed77ee4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415052"
---
# <a name="pidtagreceivefoldersettings-canonical-property"></a>PidTagReceiveFolderSettings 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件存储区的接收文件夹设置的表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECEIVE_FOLDER_SETTINGS  <br/> |
|标识符:  <br/> |0x3415  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |MAPI 邮件存储  <br/> |
   
## <a name="remarks"></a>说明

此属性可以排除在[IMAPIProp:: CopyTo](imapiprop-copyto.md)操作中, 也可以包含在[IMAPIProp:: CopyProps](imapiprop-copyprops.md)操作中。 作为 PT_OBJECT 类型的属性, [IMAPIProp:: GetProps](imapiprop-getprops.md)方法无法成功检索它;其内容应由[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法访问, 请求提供带有标识符 IID_IMAPITable 的接口。 如果设置了服务提供程序, 则必须将其报告给[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法, 但如果未设置, 则可以选择报告它。 
  
若要检索表内容, 客户端应用程序应调用[IMsgStore:: GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法。 有关详细信息, 请参阅[接收文件夹表](receive-folder-tables.md)。
  
此属性包含邮件存储区的接收文件夹的映射表。 对此属性调用**OpenProperty**等效于调用邮件存储区上的**GetReceiveFolderTable** 。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

