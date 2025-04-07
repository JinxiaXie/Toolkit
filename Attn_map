lib/test/tracker/ostrack.py的init的时候注册钩子：self.add_hook = add_hook 
def add_hook(self):
    enc_attn_weights = []
    self.network.backbone.blocks[31].attn.register_forward_hook( #进行了相关的forward之后才能钩到东西
        lambda self, input, output: enc_attn_weights.append(output[1]) #0是特征，1是注意力
        )
    self.hook = [enc_attn_weights]

#后续钩到的东西在self.hook里面
