---
title: IFolderSupport IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IFolderSupport
api_type:
- COM
ms.assetid: a4b03a66-cf6d-cd20-f1df-b247d3ee87aa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a4a1c78e65d9a515b2b42d7e0a2bc3a8b4bd8869
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775335"
---
# <a name="ifoldersupport--iunknown"></a>IFolderSupport : IUnknown

  
  
**适用于**： Outlook 
  
提供的共享文件夹的支持的信息。
  
|||
|:-----|:-----|
|提供者：  <br/> |消息存储提供程序  <br/> |
|接口标识符：  <br/> |IID_IFolderSupport  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|**[GetSupportMask](ifoldersupport-getsupportmask.md)** <br/> |获取共享文件夹的支持的信息。  <br/> |
   
## <a name="remarks"></a>说明

一般情况下，Microsoft Office Outlook 需要 MAPI 存储提供程序实现此接口，如果提供程序希望共享文件夹。 例外情况是可以实现此接口不共享文件夹的 Exchange Server 存储提供程序。
  
客户端可以查询**IFolderSupport** **[IMAPIFolder](imapifolderimapicontainer.md)** 。 如果成功，调用**IFolderSupport::GetSupportMask**并检查要设置的**FS_SUPPORTS_SHARING**位。 
  

