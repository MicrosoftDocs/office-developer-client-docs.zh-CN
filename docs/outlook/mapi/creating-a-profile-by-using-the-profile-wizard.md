---
title: 使用配置文件向导创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4b611818-f99f-43a2-9f6b-1aa5b9564d1d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a93cfb05d8abfffc9f55a7ea48efc3c3451dddbb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411734"
---
# <a name="creating-a-profile-by-using-the-profile-wizard"></a>使用配置文件向导创建配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
配置文件向导是一种 MAPI 功能，使用户能够以最简单的方式创建配置文件。 "配置文件向导"显示一系列对话框，提示用户选择邮件服务并输入一些最基本的配置属性的值。 对于大多数其他所需的属性，配置文件向导使用提供的默认值。 若要调用配置文件向导，请调用 **LaunchWizard，** 这是一个基于 [LAUNCHWIZARDENTRY 原型](launchwizardentry.md) 的函数。 
  
用户只能将那些邮件服务和服务提供程序添加到支持配置文件向导的新配置文件中。 由于每个邮件服务可能需要设置的属性数多于配置文件向导可以处理的属性数，因此请注意，如果此方法使用，则一个或多个选定服务或提供程序可能配置不完整。
  

