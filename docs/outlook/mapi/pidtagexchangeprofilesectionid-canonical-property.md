---
title: PidTagExchangeProfileSectionId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExchangeProfileSectionId
api_type:
- HeaderDef
ms.assetid: 4ad2f417-be8f-4fc8-9321-82097289074b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ce823159047410a8cea13b7eff5566cd8abaa5b9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316427"
---
# <a name="pidtagexchangeprofilesectionid-canonical-property"></a>PidTagExchangeProfileSectionId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含动态生成的 GUID，用于在使用多个帐户时确定Microsoft Exchange Server帐户。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EMSMDB_SECTION_UID  <br/> |
|标识符:  <br/> |0x3d150102  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |多个 Exchange 帐户  <br/> |
   
## <a name="remarks"></a>备注

Microsoft Outlook 2010和Microsoft Outlook 2013支持多个 Exchange 帐户，而不是一个Exchange帐户。 为了容纳多个Exchange，更改了 MAPI 配置文件布局。 在 Microsoft Office Outlook 2007 及更早版本，配置文件包含专用于 Exchange 设置（如服务器名称、用户名和脱机文件夹文件 (.ost) ）的固定配置文件部分。 location。 这些设置是使用唯一标识符 **pbGlobalProfileSectionGuid** 属性标识的。 用于全局配置文件Exchange节称为"Exchange配置文件"部分。 
  
固定配置文件分区位置不再足以容纳多个Exchange帐户。 相反，对于Exchange帐户，存在专用于该帐户的设置的部分。 用于设置的新Exchange由唯一标识符 **emsmdbUID 标识**。
  
在帐户的邮件服务配置文件Exchange，您可以找到一个属性，其中包含创建帐户时动态生成的 GUID。 此 GUID 存储在 **PidTagExchangeProfileSectionId** 属性中。 邮件存储和通讯簿容器公开一个属性，以确定Exchange属于哪个帐户。 可在邮件服务表中访问，每个Exchange服务都公开此属性。 
  
在查询以下任何接口后，可以通过调用 **PidTagExchangeProfileSectionId** 上的 [IMAPIProp：：GetProps](imapiprop-getprops.md)来检索此属性： 
  
- [IMsgStore : IMAPIProp](imsgstoreimapiprop.md)
    
- [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
    
- [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)
    
如果对象不与对象关联Exchange，则调用返回 **MAPI_E_NOT_FOUND**。
  
在显示通讯簿时，可以限制 **PidTagExchangeProfileSectionId** 上的容器。 打开容器后，可以从中查询 **emsmdbUID。** 还值得注意的是，如果从 Exchange 通讯簿中选择了收件人，则收件人的属性列表中也包含 **PidTagExchangeProfileSectionId。** 
  
> [!NOTE]
> 在整个代码示例和函数标头中，此 GUID 称为 **emsmdbUID**。 
  
其中一Exchange帐户标记为旧版Exchange帐户。 通常，它是添加到配置文件的第一个帐户。 每次调用打开 **pbGlobalProfileSectionGuid** 时都会重定向到Exchange帐户的全局部分。 与非旧帐户交互的对象模型调用Exchange与旧帐户Exchange交互。 
  
旧版 Exchange服务具有 PR_EMSMDB_LEGACY (0x3D18000B) ，在邮件服务表中设置为 **true。** 
  
旧 **emsmdbUID** 也标记在配置文件的 Outlook 全局配置文件部分作为 **PidTagExchangeProfileSectionId**。 为支持多个 Exchange 帐户编写的代码应该不需要检索旧版 **emsmdbUID，** 因为它应获取正确的 **emsmdbUID，** 具体取决于代码与之交互的帐户。
  
## <a name="see-also"></a>另请参阅



[使用多个Exchange帐户](using-multiple-exchange-accounts.md)


[如何打开"全局配置文件"部分](https://support.microsoft.com/kb/188482)

