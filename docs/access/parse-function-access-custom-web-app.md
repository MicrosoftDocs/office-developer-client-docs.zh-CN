---
title: Parse 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09dee0ae-89b2-449c-a3c8-d6b270710b64
description: 分析文本值, 并使用应用程序的区域性以给定的类型返回其值。
ms.openlocfilehash: d664985ab1d7a7d33b99c52d5bab4aa714767e40
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411132"
---
# <a name="parse-function-access-custom-web-app"></a><span data-ttu-id="2ba8a-103">Parse 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="2ba8a-103">Parse Function (Access custom web app)</span></span>

<span data-ttu-id="2ba8a-104">分析文本值, 并使用应用程序的区域性以给定的类型返回其值。</span><span class="sxs-lookup"><span data-stu-id="2ba8a-104">Parses a text value and returns its value in a given type using the culture of the application.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ba8a-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="2ba8a-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="2ba8a-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="2ba8a-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2ba8a-107">语法</span><span class="sxs-lookup"><span data-stu-id="2ba8a-107">Syntax</span></span>

 <span data-ttu-id="2ba8a-108">**分析**(*TextExpression*, *DataType*)</span><span class="sxs-lookup"><span data-stu-id="2ba8a-108">**Parse** (*TextExpression*, *DataType*)</span></span> 
  
<span data-ttu-id="2ba8a-109">**Parse**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="2ba8a-109">The **Parse** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="2ba8a-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="2ba8a-110">**Argument name**</span></span>|<span data-ttu-id="2ba8a-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2ba8a-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="2ba8a-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="2ba8a-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="2ba8a-113">表示要分析为指定数据类型的格式化值的文本表达式。</span><span class="sxs-lookup"><span data-stu-id="2ba8a-113">A text expression representing the formatted value to parse into the specified data type.</span></span>  <br/> |
| <span data-ttu-id="2ba8a-114">*DataType*</span><span class="sxs-lookup"><span data-stu-id="2ba8a-114">*DataType*</span></span>  <br/> |<span data-ttu-id="2ba8a-115">表示为结果请求的数据类型的文本值。</span><span class="sxs-lookup"><span data-stu-id="2ba8a-115">Literal value representing the data type requested for the result.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ba8a-116">说明</span><span class="sxs-lookup"><span data-stu-id="2ba8a-116">Remarks</span></span>

<span data-ttu-id="2ba8a-117">仅使用用于将字符串转换为日期/时间和数字类型的**分析**。</span><span class="sxs-lookup"><span data-stu-id="2ba8a-117">Use **Parse** only for converting from string to date/time and number types.</span></span> <span data-ttu-id="2ba8a-118">对于常规类型转换, 请使用**Convert**函数。</span><span class="sxs-lookup"><span data-stu-id="2ba8a-118">For general type conversions, use the **Convert** function.</span></span> <span data-ttu-id="2ba8a-119">请记住, 在分析字符串值时会发生一定的性能开销。</span><span class="sxs-lookup"><span data-stu-id="2ba8a-119">Keep in mind that there is a certain performance overhead in parsing the string value.</span></span> 
  

