---
title: 使用配置文件向导创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4b611818-f99f-43a2-9f6b-1aa5b9564d1d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 29a135264772847a624e1a4558b68bcf822b18df
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774726"
---
# <a name="creating-a-profile-by-using-the-profile-wizard"></a>使用配置文件向导创建配置文件

  
  
**适用于**： Outlook 
  
配置文件向导是 MAPI 功能，使用户能够创建配置文件中的最简单的可能方式。 配置文件向导显示对话框提示用户选择消息服务和输入的一些最重要的配置属性的值的一系列。 对于大多数其他必需的属性，该配置文件向导使用提供的默认值。 若要调用配置文件向导，请调用**LaunchWizard**，基于[LAUNCHWIZARDENTRY](launchwizardentry.md)原型的函数。 
  
用户可以向支持配置文件向导的新配置文件添加这些消息服务和服务提供商。 因为每个邮件服务可能需要多个属性不是配置文件向导可以处理进行设置，请注意，如果使用此方法，则可能为一个或多个选定的服务或提供商能够配置不完全。
  

