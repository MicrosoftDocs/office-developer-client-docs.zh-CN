---
title: 窗体配置文件的文件格式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 86e4ebd9-6df2-4346-9ce9-580f80a83884
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 95add2ca747a267b825648f0de82e8c8a83d3eb7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592253"
---
# <a name="file-format-of-form-configuration-files"></a><span data-ttu-id="45d49-103">窗体配置文件的文件格式</span><span class="sxs-lookup"><span data-stu-id="45d49-103">File format of form configuration files</span></span>

<span data-ttu-id="45d49-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="45d49-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="45d49-105">窗体配置文件是以定义窗体的窗体开发人员创建的带格式的文件。</span><span class="sxs-lookup"><span data-stu-id="45d49-105">A form configuration file is a formatted file created by form developers to define a form.</span></span>
  
<span data-ttu-id="45d49-106">由于表单管理员使用的窗体配置文件用于加载表单，必须使用窗体配置文件定义每个窗体。</span><span class="sxs-lookup"><span data-stu-id="45d49-106">Because form configuration files are used by form managers to load forms, each form must be defined using a form configuration file.</span></span> <span data-ttu-id="45d49-107">窗体配置文件必须.cfg 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="45d49-107">Form configuration files must have the .cfg filename extension.</span></span> <span data-ttu-id="45d49-108">文件遵循常规 Windows 初始化文件 （.ini 文件） 的语法。</span><span class="sxs-lookup"><span data-stu-id="45d49-108">The file follows the general syntax of a Windows initialization file (.ini file).</span></span> 

<span data-ttu-id="45d49-109">划分为已命名的节，并每部分都包含一系列项和值。</span><span class="sxs-lookup"><span data-stu-id="45d49-109">It is divided into named sections, and each section contains a series of entries and values.</span></span> <span data-ttu-id="45d49-110">值具有以下类型之一： 字符串、 显示的字符串、 平台字符串、 路径、 整数或**GUID**的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="45d49-110">Values have one of the following types: string, displayed string, platform string, path, integer, or globally unique identifier, **GUID**.</span></span> <span data-ttu-id="45d49-111">可以使用任何文本编辑器或能够保存文本文件的字处理程序创建窗体配置文件。</span><span class="sxs-lookup"><span data-stu-id="45d49-111">Form configuration files can be created with any text editor or word processor that is capable of saving text files.</span></span>
  

