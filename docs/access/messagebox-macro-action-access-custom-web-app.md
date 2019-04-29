---
title: MessageBox 宏操作 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: bdacdafc-728b-4952-b28a-b5c1fe4b4f63
description: 可以使用 MessageBox 操作显示包含警告或信息性消息的消息框。 例如, 可以将 MessageBox 操作与验证宏一起使用。 当控件或记录未通过宏的有效性验证条件时, 消息框会显示一条错误消息, 并提供有关应输入的数据类型的说明。
ms.openlocfilehash: 9f45101fd269ef863e60fd8e69741e5cd7c56ef1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433449"
---
# <a name="messagebox-macro-action-access-custom-web-app"></a><span data-ttu-id="7bdab-105">MessageBox 宏操作 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="7bdab-105">MessageBox Macro Action (Access custom web app)</span></span>

<span data-ttu-id="7bdab-106">可以使用**MessageBox**操作显示包含警告或信息性消息的消息框。</span><span class="sxs-lookup"><span data-stu-id="7bdab-106">You can use the **MessageBox** action to display a message box containing a warning or an informational message.</span></span> <span data-ttu-id="7bdab-107">例如, 可以将**MessageBox**操作与验证宏一起使用。</span><span class="sxs-lookup"><span data-stu-id="7bdab-107">For example, you can use the **MessageBox** action with validation macros.</span></span> <span data-ttu-id="7bdab-108">当控件或记录未通过宏的有效性验证条件时, 消息框会显示一条错误消息, 并提供有关应输入的数据类型的说明。</span><span class="sxs-lookup"><span data-stu-id="7bdab-108">When a control or record fails a validation condition in the macro, a message box can display an error message and provide instructions about the kind of data that should be entered.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7bdab-p103">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="7bdab-p103">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="7bdab-111">设置</span><span class="sxs-lookup"><span data-stu-id="7bdab-111">Setting</span></span>

<span data-ttu-id="7bdab-112">**MessageBox**操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="7bdab-112">The **MessageBox** action has the following argument.</span></span> 
  
|<span data-ttu-id="7bdab-113">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="7bdab-113">**Action argument**</span></span>|<span data-ttu-id="7bdab-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="7bdab-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7bdab-115">邮件</span><span class="sxs-lookup"><span data-stu-id="7bdab-115">Message</span></span>  <br/> |<span data-ttu-id="7bdab-116">消息框中的文本。</span><span class="sxs-lookup"><span data-stu-id="7bdab-116">The text in the message box.</span></span> <span data-ttu-id="7bdab-117">最长可键入255个字符或输入一个表达式 (前面加上等号)。</span><span class="sxs-lookup"><span data-stu-id="7bdab-117">You can type up to 255 characters or enter an expression (preceded by an equal sign).</span></span>  <br/> |
   

