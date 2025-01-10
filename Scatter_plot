import numpy as np
import matplotlib.pyplot as plt
import matplotlib.axes._axes as axes
import matplotlib.figure as figure
# from matplotlib.backends.backend_pdf import PdfPages
# pdf = PdfPages('speed-eao2018.pdf')
# plt.rc('font',family='Times New Roman')


fig, ax = plt.subplots()  # type:figure.Figure, axes.Axes
ax.set_title('Comparison of Performance, Params, and FLOPs on LaSOT', fontsize=15)
ax.set_xlabel('Params', fontsize=15)
ax.set_ylabel('AUC', fontsize=15)


trackers =['ODTrack-B', 'SeqTrack-B384', 'ARTrack384', 'HIPTrack', 'MixFormer-L', 'CTTrack-B', 'Ours-384']
speed = np.array([92, 89, 173, 120, 183.9, 93.8,70]) #params
qipao_norm = np.array([73,148,83,66.9, 127.8, 48.1, 55.7]) / 90 #floats
performance = np.array([0.732, 0.715, 0.726, 0.727, 0.701, 0.678,0.731])#np.array([0.273, 0.286, 0.380, 0.401, 0.414, 0.440, 0.438, 0.467, 0.490])

circle_color = [ 'deepskyblue','b', 'turquoise', 'green', 'cornflowerblue', 'fuchsia', 'r']# 'yellowgreen']#, 'green']

# Marker size in units of points^2 控制气泡的大小
volume = (300 * qipao_norm/5 * performance/0.6)  ** 2 

#气泡
ax.scatter(speed, performance, c=circle_color, s=volume, alpha=0.4)
#每个圆心
ax.scatter(speed, performance, c=circle_color, s=20, marker='o') 

# 标上跟踪器的名字
ax.text(speed[0] -10, performance[0] - 0.007, trackers[0], fontsize=13, color='k')
ax.text(speed[1] - 15,performance[1] - 0.006, trackers[1], fontsize=13, color='k')
ax.text(speed[2] -14, performance[2] - 0.006, trackers[2], fontsize=13, color='k')
ax.text(speed[3] - 7, performance[3] - 0.006, trackers[3], fontsize=13, color='k')
ax.text(speed[4] - 18,performance[4] - 0.006, trackers[4], fontsize=13, color='k')
ax.text(speed[5] -11, performance[5] - 0.006, trackers[5], fontsize=13, color='k')
ax.text(speed[6] - 11, performance[6] -0.004, trackers[6], fontsize=13, color='r')

ax.grid(which='major', axis='both', linestyle='-.') # color='r', linestyle='-', linewidth=2
ax.set_xlim(60, 190)
ax.set_ylim(0.65, 0.75)
ax.xaxis.set_tick_params(labelsize=12)
ax.yaxis.set_tick_params(labelsize=12)

ystart, yend = ax.get_ylim()
# 画线，两个点为[xstar,xend],[ystart, yend]
#ax.plot([25, 25], [ystart, yend], linestyle="--", color='k', linewidth=0.7) #实时跟踪的竖线
# ax.plot([70, 80], [0.70,  0.72], linestyle="--", color='r', linewidth=0.7) #x轴25到58，Y轴0.49到0.467
#ax.text(26, 0.550 , 'Real-time line', fontsize=11, color='k') #写字

plt.savefig('./scatter_plot.pdf')
#fig.savefig('speed-eao2018.svg')


#pdf.savefig()
#pdf.close()
#plt.show()

