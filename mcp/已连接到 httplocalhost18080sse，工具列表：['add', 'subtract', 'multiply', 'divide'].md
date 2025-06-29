已连接到 http://localhost:18080/sse，工具列表：['add', 'subtract', 'multiply', 'divide']

MCP 客户端已启动，输入你的问题，输入 'quit' 退出。

问题: 计算3加5

收集所有可用工具:meta=None nextCursor=None tools=[Tool(name='add', description='\n    Add two numbers.\n\n    Parameters:\n    - a (float): First number (
required)\n    - b (float): Second number (required)\n\n    Returns:\n    - float: The result of a + b\n    ', inputSchema={'properties': {'a': {'title': 'A', 'type': 'number'}, 'b': {'title': 'B', 'type': 'number'}}, 'required': ['a', 'b'], 'title': 'addArguments', 'type': 'object'}, annotations=None), Tool(name='subtract', description='\n    Subtract two numbers.\n\n    Parameters:\n    - a (float): The number to subtract from (required)\n    - b (float): The number to subtract (required)\n\n    Returns:\n    - float: The result of a - b\n    ', inputSchema={'properties': {'a': {'title': 'A', 'type': 'number'}, 'b': {'title': 'B', 'type': 'number'}}, 'required': ['a', 'b'], 'title': 'subtractArguments', 'type': 'object'}, annotations=None), Tool(name='multiply', description='\n    Multiply two numbers.\n\n    Parameters:\n    - a (float): First number (required)\n    - b (float): Second number (required)\n\n    Returns:\n    - float: The result of a * b\n    ', inputSchema={'properties': {'a': {'title': 'A', 'type': 'number'}, 'b': {'title': 'B', 'type': 'number'}}, 'required': ['a', 'b'], 'title': 'multiplyArguments', 'type': 'object'}, annotations=None), Tool(name='divide', description='\n    Divide two numbers.\n\n    Parameters:\n    - a (float): Numerator (required)\n    - b (float): Denominator (required, must not be zero)\n\n    Returns:\n    - float: The result of a / b\n    ', inputSchema={'properties': {'a': {'title': 'A', 'type': 'number'}, 'b': {'title': 'B', 'type': 'number'}}, 'required': ['a', 'b'], 'title': 'divideArguments', 'type': 'object'}, annotations=None)]

向模型发送初始请求:ChatCompletion(id='0197bc80db67025356afb07b24b4903a', choices=[Choice(finish_reason='tool_calls', index=0, logprobs=None, message=ChatCMessage(content='\n我将调用 `server0_add` 函数来计算数字 3 和 5 的和。', refusal=None, role='assistant', annotations=None, audio=None, function_call=None,atCompletionMessageToolCall(id='0197bc811bd0961b37fffee939f81d28', function=Function(arguments='{"a": 3, "b": 5}', name='server0_add'), type='function', index=0)], reasoning_content='\n我们需要计算3加5，所以使用server0_add函数，传入a=3, b=5\n 注意：函数名中的server0是前缀，我们直接调用提供的函数名即可。\n 由中，我们不需要手动构建函数调用的HTTP请求，而是直接使用已经封装好的函数。\n 但是，由于我们是在模拟环境中，我们只需要按照指定的方式调用函数，这里我们使用server0_add(a=3, b=5)\n 然而，在思考过程中，我们
输出的是函数调用的参数，但实际调用是由环境执行的。\n\n 因此，我们直接调用函数server0_add，并传递参数a=3, b=5。\n'))], created=1751214251, model='deepseek-service_tier=None, system_fingerprint='', usage=CompletionUsage(completion_tokens=196, prompt_tokens=616, total_tokens=812, completion_tokens_details=CompletionTokensDetails(accepted_prediction_tokens=None, audio_tokens=None, reasoning_tokens=162, rejected_prediction_tokens=None), prompt_tokens_details=None))

处理工具调用:[{'role': 'user', 'content': '计算3加5'}, {'role': 'assistant', 'tool_calls': [{'id': '0197bc811bd0961b37fffee939f81d28', 'type': 'function',
 'function': {'name': 'server0_add', 'arguments': '{"a": 3, "b": 5}'}}]}, {'role': 'tool', 'tool_call_id': '0197bc811bd0961b37fffee939f81d28', 'content': "[TextContent(type='text', text='8.0', annotations=None)]"}]


我将调用 `server0_add` 函数来计算数字 3 和 5 的和。
[调用工具 server0_add 参数: {'a': 3, 'b': 5}]
工具结果: [TextContent(type='text', text='8.0', annotations=None)]

3加5的计算结果为8.0。