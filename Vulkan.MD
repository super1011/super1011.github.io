1. 针对DescriptorSetLayout, DescriptorSetPool, DescriptorSet 这几个对象之间的关系。
   仔细理解后。目前得出一些结论
     DescriptorSetLayout 创建时如果使用了多个Binding， 那么这多个binding 就相当于组合到了一起，都会存在于这个layout中， 之后在创建 SetPool时， 
这里的bingding数量会直接影响到创建pool时的 poolSize 对象的数量。每个poolSize，多个poolSize时， 创建的pool 会根据每个poolSize的 count 计算出总count，确保可以提供足够的数量的对象。
