---
title: Try_Parse 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed35263c-b0ad-4269-9caa-c0164015e980
description: 分析到指定的数据类型的区域性中的应用程序的文本值或返回 Null，如果转换无效。
ms.openlocfilehash: 3446e928d9772641f9aea7b956e142f995824b1e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773625"
---
# <a name="tryparse-function-access-custom-web-app"></a><span data-ttu-id="1f7dc-103">Try_Parse 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="1f7dc-103">Try_Parse Function (Access custom web app)</span></span>

<span data-ttu-id="1f7dc-104">分析到指定的数据类型的区域性中的应用程序的文本值或返回 Null，如果转换无效。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-104">Parses a text value to the specified data type in the culture of the application or returns Null if the conversion is not valid.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f7dc-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="1f7dc-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="1f7dc-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1f7dc-107">语法</span><span class="sxs-lookup"><span data-stu-id="1f7dc-107">Syntax</span></span>

 <span data-ttu-id="1f7dc-108">**Try_Parse**(*TextExpression*，*数据类型*)</span><span class="sxs-lookup"><span data-stu-id="1f7dc-108">**Try_Parse** (*TextExpression*, *DataType*)</span></span> 
  
<span data-ttu-id="1f7dc-109">**Try_Parse**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-109">The **Try_Parse** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="1f7dc-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="1f7dc-110">**Argument name**</span></span>|<span data-ttu-id="1f7dc-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1f7dc-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1f7dc-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="1f7dc-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="1f7dc-113">一个文本表达式，表示要分析到指定的数据类型的格式化的值。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-113">A text expression representing the formatted value to parse into the specified data type.</span></span>  <br/> |
| <span data-ttu-id="1f7dc-114">*数据类型*</span><span class="sxs-lookup"><span data-stu-id="1f7dc-114">*DataType*</span></span>  <br/> |<span data-ttu-id="1f7dc-115">要分析*TextExpression*将数据类型。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-115">The data type into which to parse  *TextExpression*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f7dc-116">备注</span><span class="sxs-lookup"><span data-stu-id="1f7dc-116">Remarks</span></span>

<span data-ttu-id="1f7dc-117">**Try_Parse**仅用于从字符串转换为日期/时间和号码的类型。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-117">Use **Try_Parse** only for converting from string to date/time and number types.</span></span> <span data-ttu-id="1f7dc-118">常规类型转换，继续使用**转换**。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-118">For general type conversions, continue to use **Convert**.</span></span> 
  

