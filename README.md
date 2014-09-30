ngx_lua_consistent
==================

consistent hash power by ngx_lua.
I'm sorry that my English is very poor, but I will stick to in English, so if you have some question, connect me:

QQ:804368954
email:804368954@qq.com

Thank you!

How to use:
==================

  local servers = {192.168.0.3, 192.168.3.1, 192.168.0.2};
  local consistent = require 'consistent';
  
  consistent.add_server(servers);
  local key = 'http://baidu.com/haha';
  local ip = consistent.get_upstream(key); --one of the servers
  
Test
=======
local consistent = require 'resty.consistent';
consistent.add_server({'127.0.0.1', '127.0.0.2'});
local a,b = 1,1;
for i=1, 10000 do 
    local ser = consistent.get_upstream(math.random());
    if ser == '127.0.0.1' then
        a = a+1;
    else    
        b = b+1;
    end
end
ngx.say(a,','b); --5404,4598
  
